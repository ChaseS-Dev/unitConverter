<!-- 1 meter = 3.281 feet
1 liter = 0.264 gallon
1 kilogram = 2.204 pound -->
<script>
  let clicked = false;
  let input = 0;
  let lengthTextMetric = 0;
  let volumeTextMetric = 0;
  let massTextMetric = 0;
  let lengthTextImperial = 0;
  let volumeTextImperial = 0;
  let massTextImperial = 0;

  function convertToMetric() {
    lengthTextMetric = (input * 3.281).toFixed(3);
    volumeTextMetric = (input * 0.264).toFixed(3);
    massTextMetric = (input * 2.204).toFixed(3);
    console.log("convertToMetric function ran");
  }

  function convertToImperial() {
    lengthTextImperial = (input / 3.281).toFixed(3);
    volumeTextImperial = (input / 0.264).toFixed(3);
    massTextImperial = (input / 2.204).toFixed(3);
    console.log("convertToImperial function ran");
  }

  function activate() {
    convertToImperial();
    convertToMetric();
    return (clicked = true);
  }
</script>

<div id="topContainer">
  <div class="top">
    <h1 id="title">Metric/Imperial Unit Conversion</h1>
    <div>
      <input id="inputEl" bind:value={input} />
    </div>
    <div>
      <button id="convert" on:click={activate}>Convert</button>
    </div>
  </div>
</div>
<div id="bottomContainer">
  <div class="bottom">
    <div class="backBox" id="length">
      <h2 id="length">Length (Meter/Feet)</h2>
      <p class={clicked === true ? "fadeIn" : "hidden"} id="lengthText">
        {input} meters = {lengthTextMetric} feet | {input} feet = {lengthTextImperial}
        meters
      </p>
    </div>
    <div class="backBox" id="volume">
      <h2 id="volume">Volume (Liter/Gallon)</h2>
      <p class={clicked === true ? "fadeIn" : "hidden"} id="volumeText">
        {input} liters = {volumeTextMetric} gallons | {input} gallons = {volumeTextImperial}
        liters
      </p>
    </div>
    <div class="backBox" id="mass">
      <h2 id="mass">Mass (Kilogram/Pound)</h2>
      <p class={clicked === true ? "fadeIn" : "hidden"} id="massText">
        {input} kilos = {massTextMetric} pounds | {input} pounds = {massTextImperial}
        kilos
      </p>
    </div>
  </div>
</div>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;800&display=swap");

  :global(body) {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    justify-content: center;
    font-family: "Inter", sans-serif;
    margin: 0;
    background-color: #1f2937;
  }
  #topContainer {
    background-color: #6943ff;
    color: white;
    width: 100%;
  }

  #title {
    font-weight: 800;
    font-size: 28px;
    line-height: 38px;
    letter-spacing: -1px;
    padding: 30px 50px;
  }

  #inputEl {
    font-weight: 800;
    font-size: 58px;
    color: white;
    background-color: #6943ff;
    text-align: center;
    border: 2px solid #b295ff;
    border-radius: 5px;
    height: 80px;
    width: 115px;
    margin-bottom: 25px;
  }

  #convert {
    font-weight: 600;
    color: #3d3d3d;
    font-size: 16px;
    border-radius: 5px;
    border: 0px;
    height: 40px;
    width: 117px;
    margin-bottom: 35px;
  }

  #bottomContainer {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: #1f2937;
    width: 100%;
    padding-top: 20px;
    padding-bottom: 20px;
  }

  .backBox {
    background-color: #273549;
    margin: 25px 25px;
    height: 110px;
    padding-top: 15px;
    width: 45vw;
  }

  #length {
    font-weight: 600;
    color: #ccc1ff;
  }

  #lengthText {
    color: white;
    font-size: 14px;
    font-weight: 400;
  }

  #volume {
    font-weight: 600;
    color: #ccc1ff;
  }

  #volumeText {
    color: white;
    font-size: 14px;
    font-weight: 400;
  }

  #mass {
    font-weight: 600;
    color: #ccc1ff;
  }

  #massText {
    color: white;
    font-size: 14px;
    font-weight: 400;
  }

  .hidden {
    opacity: 0;
    transform: translate3d(50px, 0, 0); /* ADDED - start x position as -50px */
  }

  .fadeIn {
    opacity: 1;
    transform: translate3d(0, 0, 0); /* ADDED - start x position as -50px */
    cursor: pointer;
    transition: 0.25s all ease-in-out;
  }
</style>
