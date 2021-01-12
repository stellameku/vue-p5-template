<template>
  <div class="container">
    <div class="p5Canvas">
    </div>
  </div>
</template>

<script>
import P5 from 'p5';

export default {
  data() {
    return {
      p5Canvas: null,
    }
  },
  created() {
    const sketch = p5 => {
        let w = 500;
        let h = 400;


        // let w = window.innerWidth;
        // let h = window.innerHeight;

        p5.setup = () => {
            p5. createCanvas(710, 400, p5.WEBGL);

        };

        p5.draw = () => {
            p5.background(250);
            p5.translate(-240, -100, 0);
            p5.normalMaterial();
           

            p5.translate(240, 0, 0);
            p5.push();
            p5.rotateZ(p5.frameCount * 0.01);
            p5.rotateX(p5.frameCount * 0.01);
            p5.rotateY(p5.frameCount * 0.01);
            p5.box(70, 70, 70);
            p5.pop();

            p5.translate(240, 0, 0);
            p5.push();
            p5.rotateZ(p5.frameCount * 0.01);
            p5.rotateX(p5.frameCount * 0.01);
            p5.rotateY(p5.frameCount * 0.01);
            p5.cylinder(70, 70);
            p5.pop();

            p5.translate(-240 * 2, 200, 0);
            p5.push();
            p5.rotateZ(p5.frameCount * 0.01);
            p5.rotateX(p5.frameCount * 0.01);
            p5.rotateY(p5.frameCount * 0.01);
            p5.cone(70, 70);
            p5.pop();

            p5.translate(240, 0, 0);
            p5.push();
            p5.rotateZ(p5.frameCount * 0.01);
            p5.rotateX(p5.frameCount * 0.01);
            p5.rotateY(p5.frameCount * 0.01);
            p5.torus(70, 20);
            p5.pop();

        };

       
    }

    this.p5Canvas = new P5(sketch, 'p5Canvas');
  },
  unmounted () {
    this.p5Canvas = null;
  },
}
</script>

<style>
#p5Canvas {
  width: 100vw;
  position: relative;
}

main {
  margin: 0 auto;
  width: 90vw;
}
</style>