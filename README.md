# Lilac-salamander
It's real

![buh](https://github.com/nicolasbaez/Lilac-salamander/blob/main/xp019.gif)
```javascript
setup = (_) => {
  createCanvas((w = 500), w, WEBGL);
  k = 0;
};
draw = (_) => {
  if (k < 6) {
    rotateX(k);
    noFill();
    strokeWeight(4);
    stroke(255, random(32), 128, map(sin(k), 0, 1, 0, 99));
    beginShape();
    for (i = -w; i < w; i += w / 9) {
      curveVertex(i, noise(i, k) * w * 0.4);
    }
    endShape();
    k += 0.03;
  } else {
    clear();
    noiseSeed();
    k = 0;
  }
};
keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp019.gif", 800, { delay: 0, units: "frames" });
  }
};
