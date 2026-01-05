let lastMinute = -1;

function setup() {
  createCanvas(800, 800);
  angleMode(RADIANS);
  colorMode(HSB, 360, 100, 100, 100);
  noStroke();
}

function draw() {
  background(8);

  const h = hour() % 12;  
  const m = minute();      
  const s = second();      

  if (m !== lastMinute) {
    console.log(m);
    lastMinute = m;
  }

  translate(width / 2, height / 2);

  const rHour = 120;  
  const rMin  = 230;
  const rSec  = 320;

  drawTrailArc(h, 12, rHour, 175, 100, 7); 
  drawTrailArc(m, 60, rMin, 150, 95, 6);   
  drawTrailArc(s, 60, rSec, 110, 90, 5);   
}

function drawTrailArc(value, maxValue, r, trailDegrees, steps, dotSize) {
  const aNow = -HALF_PI + (TWO_PI * value) / maxValue;
  const trailRad = radians(trailDegrees);

  for (let i = 0; i < steps; i++) {
    const t = i / (steps - 1);          
    const a = aNow - trailRad * (1 - t); 

    const x = cos(a) * r;
    const y = sin(a) * r;

    const alpha = lerp(4, 34, t);

    const sz = lerp(dotSize * 0.75, dotSize * 1.3, t);

    const hue = hueFromAngle(a);

    fill(hue, 82, 92, alpha);
    ellipse(x, y, sz);
  }
}
function hueFromAngle(a) {
  let norm = (a + HALF_PI) / TWO_PI;
  norm = (norm + 1) % 1;

  const mix = sin(norm * PI);
  return lerp(210, 20, mix);
}
