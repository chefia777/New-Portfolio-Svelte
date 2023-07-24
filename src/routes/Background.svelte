<script>
  import "./styles.css";
  import "../app.css";
  import sun from "$lib/images/sun.png";
  import mercury from "$lib/images/mercury.png";
  import venus from "$lib/images/venus.png";
  import earth from "$lib/images/earth.png";
  import mars from "$lib/images/mars.png";
  import jupiter from "$lib/images/jupiter.png";
  import saturn from "$lib/images/saturn.png";
  import uranus from "$lib/images/uranus.png";
  import neptune from "$lib/images/neptune.png";
  import pluto from "$lib/images/pluto.png";
</script>

<div class="bg">
  <div class="system">
    <div class="system__orbit system__orbit--sun">
      <img src={sun} alt="Sun" class="system__icon system__icon--sun" />
    </div>

    <div class="system__orbit system__orbit--mercury">
      <div class="system__planet system__planet--mercury">
        <img src={mercury} alt="Mercury" />
      </div>
    </div>
    <div class="system__orbit system__orbit--venus">
      <div class="system__planet system__planet--venus">
        <img src={venus} alt="Venus" />
      </div>
    </div>
    <div class="system__orbit system__orbit--earth">
      <div class="system__planet system__planet--earth">
        <img src={earth} alt="Earth" />
      </div>
    </div>
    <div class="system__orbit system__orbit--mars">
      <div class="system__planet system__planet--mars">
        <img src={mars} alt="Mars" />
      </div>
    </div>
    <div class="system__orbit system__orbit--jupiter">
      <div class="system__planet system__planet--jupiter">
        <img src={jupiter} alt="Jupiter" />
      </div>
    </div>
    <div class="system__orbit system__orbit--saturn">
      <div class="system__planet system__planet--saturn">
        <img src={saturn} alt="Saturn" />
      </div>
    </div>
    <div class="system__orbit system__orbit--uranus">
      <div class="system__planet system__planet--uranus">
        <img src={uranus} alt="Uranus" />
      </div>
    </div>
    <div class="system__orbit system__orbit--neptune">
      <div class="system__planet system__planet--neptune">
        <img src={neptune} alt="Neptune" />
      </div>
    </div>
    <div class="system__orbit system__orbit--pluto">
      <div class="system__planet system__planet--pluto">
        <img src={pluto} alt="Pluto" />
      </div>
    </div>
  </div>
</div>

<style lang="postcss">
  .header {
    z-index: 9999;
  }

  html {
    box-sizing: border-box;
    font-size: 62.5%;
  }
  html *,
  html *:before,
  html *:after {
    box-sizing: inherit;
  }
  body {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
    background-color: #251c2d;
  }
  .system {
    position: relative;
    width: 100%;
    max-width: 700px;
    padding-top: 100%;
    opacity: 0.5;
  }
  @media (min-width: 700px) {
    .system {
      padding-top: 700px;
    }
  }
  
  .system__orbit {
    position: absolute;
    top: 50%;
    left: 50%;
    border: 1px solid rgba(255, 255, 255, 0.3);
    border-radius: 100%;
    transform: translate(-50%, -50%);
    animation: spin infinite linear both;
  }
  .system__orbit:nth-child(1) {
    width: calc(9%);
    height: calc(9%);
  }
  .system__orbit:nth-child(2) {
    width: calc(13%);
    height: calc(13%);
  }
  .system__orbit:nth-child(3) {
    width: calc(20%);
    height: calc(20%);
  }
  .system__orbit:nth-child(4) {
    width: calc(30%);
    height: calc(30%);
  }
  .system__orbit:nth-child(5) {
    width: calc(44%);
    height: calc(44%);
  }
  .system__orbit:nth-child(6) {
    width: calc(60%);
    height: calc(60%);
  }
  .system__orbit:nth-child(7) {
    width: calc(80%);
    height: calc(80%);
  }
  .system__orbit:nth-child(8) {
    width: calc(104%);
    height: calc(104%);
  }
  .system__orbit:nth-child(9) {
    width: calc(130%);
    height: calc(130%);
  }
  .system__orbit:nth-child(10) {
    width: calc(160%);
    height: calc(160%);
  }
  .system__orbit--sun {
    border: none;
  }

  .system__orbit--mercury {
    animation-duration: 1s;
  }
  .system__orbit--venus {
    animation-duration: 2.6s;
  }
  .system__orbit--earth {
    animation-duration: 4.1s;
  }
  .system__orbit--mars {
    animation-duration: 7.8s;
  }
  .system__orbit--jupiter {
    animation-duration: 49.8s;
  }
  .system__orbit--saturn {
    animation-duration: 120.3s;
  }
  .system__orbit--uranus {
    animation-duration: 348.4s;
  }
  .system__orbit--neptune {
    animation-duration: 684.4s;
  }
  .system__orbit--pluto {
    animation-duration: 1028.6s;
  }
  .system__planet {
    position: absolute;
    top: 50%;
    left: -12px;
    width: 25px;
    height: 25px;
    border-radius: 100%;
    transform: translateY(-50%);
  }
  .system__icon {
    width: 100%;
    height: 100%;
  }
  @keyframes spin {
    from {
      transform: translate(-50%, -50%);
    }
    to {
      transform: translate(-50%, -50%) rotate(-360deg);
    }
  }

  .bg {
    position: fixed;
    z-index: 999;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    animation: loading 4s;
  }

  :global(body) {
    background: black;
  }

  .app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  main {
    flex: 1;
    display: flex;
    flex-direction: column;
    padding: 1rem;
    width: 100%;
    max-width: 64rem;
    margin: 0 auto;
    box-sizing: border-box;
  }

  footer {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 12px;
  }

  footer a {
    font-weight: bold;
  }

  @media (min-width: 480px) {
    footer {
      padding: 12px 0;
    }
  }
</style>
