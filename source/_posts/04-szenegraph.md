---
title: Szenegraph
---
In WebGL gibt es keine eingebaute Möglichkeit für Szenegraphen. Daher müssen wir uns eigene Hilfsfunktionen schreiben, um einen Szenegraphen darzustellen.

## Struktur erstellen

Zuerst benötigen wir eine Datenstruktur, mit deren Hilfe wir den Szenegraphen aufbauen können. Dazu definieren wir einen Knoten:

```js
var Node = function() {
  this.children = [];
  this.localMatrix = math.eye(4);
  this.worldMatrix = math.eye(4);
};
```

Nun benötigen wir eine Funktion, mit der man den Parent setzen kann:

```js
Node.prototype.setParent = function(parent) {
  if (this.parent) {
    var i = this.parent.children.indexOf(this);

    if (i >= 0) {
      this.parent.children.splice(i, 1);
    }
  }

  if (parent) {
    parent.children.append(this);
  }

  this.parent = parent;
};
```

Jetzt brauchen wir die Möglichkeit, die Weltmatrix anhand der Lokalmatrizen der Kinder zu aktualisieren:

```js
Node.prototype.updateWorldMatrix = function(parentWorldMatrix) {
  if (parentWorldMatrix) {
    this.worldMatrix = math.multiply(this.localMatrix, parentWorldMatrix);
  } else {
    this.localMatrix = this.worldMatrix;
  }

  var worldMatrix = this.worldMatrix;
  this.children.forEach(function(child) {
    child.updateWorldMatrix(worldMatrix);
  });
};
```

## Beispieldaten

TODO
