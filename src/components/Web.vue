<template>
  <!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Prueba técnica SDG</title>
    <link rel="stylesheet" type="text/css" href="style.css">
    <link href="https://fonts.googleapis.com/css?family=Open+Sans:400,600,700,800&display=swap" rel="stylesheet">
  </head>
  <body>
  <div id="wrap">
    <div id="wrap-icons">
      <div class="div-icon">
        <svg style="width:50px;height:50px" viewBox="0 0 24 24">
            <path fill="currentColor" d="M4,18V20H8V18H4M4,14V16H14V14H4M10,18V20H14V18H10M16,14V16H20V14H16M16,18V20H20V18H16M2,22V8L7,12V8L12,12V8L17,12L18,2H21L22,12V22H2Z" />
        </svg>
        <h1>Fractonation & intermediate processing</h1>
      </div>
      <div class="div-icon">
        <svg style="width:50px;height:50px" viewBox="0 0 24 24">
            <path fill="currentColor" d="M4.22,11.29L11.29,4.22C13.64,1.88 17.43,1.88 19.78,4.22C22.12,6.56 22.12,10.36 19.78,12.71L12.71,19.78C10.36,22.12 6.56,22.12 4.22,19.78C1.88,17.43 1.88,13.64 4.22,11.29M5.64,12.71C4.59,13.75 4.24,15.24 4.6,16.57L10.59,10.59L14.83,14.83L18.36,11.29C19.93,9.73 19.93,7.2 18.36,5.64C16.8,4.07 14.27,4.07 12.71,5.64L5.64,12.71Z" />
        </svg>
        <h1>Supplying plant incl. packaging</h1>
      </div>
    </div>
    <div id="wrap-square">
      <Square id="first" firstColor="green" secondColor="red" brand="KAN" firstNumber="0" secondNumber="55.1%" />

      <Square id="second" firstColor="green" secondColor="yellow" brand="BMW" firstNumber="0" secondNumber="86.7%" />

      <Square id="third" firstColor="red" secondColor="green" brand="BRN" firstNumber="2" secondNumber="97.4%" />
      
      <Square id="fourth" firstColor="red" secondColor="yellow" brand="BRN" firstNumber="2" secondNumber="86.4%" />  
    </div>
  </div>
  </body>
</html>
</template>

<script>
  import Square from './Square.vue'

  export default {
    name: 'Web',
    components: {
      Square
    },
    mounted () {
      setTimeout(()=>{
         this.loadArrows()
      }, 500)
    },
    methods: {
      loadArrows() {
          new window.LeaderLine(
          window.LeaderLine.pointAnchor(document.getElementById('first'), {
            x: '100%',
            y: 75
          }),
          window.LeaderLine.pointAnchor(document.getElementById('second'), {
            x: 0,
            y: 75
          }),
          {
            color: '#BCB7B7',
            size: 1,
            dash: {len: 3, gap: 5},
            endPlug: 'arrow2',
            endPlugSize: 3,
            startLabel: window.LeaderLine.captionLabel({
              text: 'OTIF',
              color: '#fff',
              outlineColor: 'none',
              fontFamily: 'Open Sans, sans-serif',
              fontWeight: 700,
              fontSize: '17px',
              offset: [35, -70]
            }),
            endLabel: window.LeaderLine.captionLabel({
              text: '63.0%',
              color: '#E93325',
              outlineColor: 'none',
              fontFamily: 'Open Sans, sans-serif',
              fontWeight: 700,
              fontSize: '24px',
              offset: [-90, -50]
            })
          }
        );

        new window.LeaderLine(
          window.LeaderLine.pointAnchor(document.getElementById('first'), {
            x: '100%',
            y: 160
          }),
          window.LeaderLine.pointAnchor(document.getElementById('fourth'), {
            x: 0,
            y: '30%'
          }),
            {
              path: 'grid',
              color: '#BCB7B7',
              size: 1,
              dash: {len: 3, gap: 5},
              endPlug: 'arrow2',
              endPlugSize: 3,
              startLabel: window.LeaderLine.captionLabel({
                text: 'OTIF',
                color: '#fff',
                outlineColor: 'none',
                fontFamily: 'Open Sans, sans-serif',
                fontWeight: 700,
                fontSize: '17px',
                offset: [35, -60]
              }),
              endLabel: window.LeaderLine.captionLabel({
                text: '20.4%',
                color: '#E93325',
                outlineColor: 'none',
                fontFamily: 'Open Sans, sans-serif',
                fontWeight: 700,
                fontSize: '24px',
                offset: [-90, -190]
              }),
              startSocket: 'right',
              endSocket: 'left',
              pointAnchor: {x: 50, y: 50}
            }        
        );

        new window.LeaderLine(
          document.getElementById('first'),
          document.getElementById('third'),
          {
            color: '#BCB7B7',
            size: 1,
            dash: {len: 3, gap: 5},
            endPlug: 'behind'
          }
        );

        new window.LeaderLine(
          window.LeaderLine.pointAnchor(document.getElementById('third'), {
            x: '100%',
            y: '70%'
          }),
          window.LeaderLine.pointAnchor(document.getElementById('fourth'), {
            x: '0%',
            y: '70%'
          }),
          {
            color: '#BCB7B7',
            size: 1,
            dash: {len: 3, gap: 5},
            endPlug: 'arrow2',
            endPlugSize: 3,
            startLabel: window.LeaderLine.captionLabel({
              text: 'OTIF',
              color: '#fff',
              outlineColor: 'none',
              fontFamily: 'Open Sans, sans-serif',
              fontWeight: 700,
              fontSize: '17px',
              offset: [35, -60]
            }),
            endLabel: window.LeaderLine.captionLabel({
              text: '-',
              color: '#EBB43E',
              outlineColor: 'none',
              fontFamily: 'Open Sans, sans-serif',
              fontWeight: 700,
              fontSize: '17px',
              offset: [-60, -40]
            }),
          }
        );

        new window.LeaderLine(
          document.getElementById('second'),
          document.getElementById('fourth'),
          {
            color: '#BCB7B7',
            size: 1,
            dash: {len: 3, gap: 5},
            endPlug: 'behind'
          }
        );
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
html {
  font-family: 'Open Sans', sans-serif;
  font-size: 13px;
  font-weight: 700;
}

p {
  font-size: 13px;
  margin-bottom: 0;
}

h1 {
  font-size: 13px;
}

#wrap {
  width: 566px;
  height: 750px;
  background-color: #2C2C2C;
  color: #BCB7B7;
  font-family: 'Open Sans', sans-serif;
}

#wrap-icons {
  display: inline-flex;
  width: 100%;
}

.div-icon {
  width: 50%;
  text-align: center;
  text-transform: uppercase;
  margin-top: 5%;
  padding: 0 10%;
}

#wrap-square {
  width: 100%;
  display: inline-flex;
  flex-wrap: wrap;
  justify-content: center;
  margin-top: 9%;
}


</style>
