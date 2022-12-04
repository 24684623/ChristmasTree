<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">

  <title>Musical Christmas Lights</title>

  <style>
    button,
    hr,
    input {
      overflow: visible
    }

    audio,
    canvas,
    progress,
    video {
      display: inline-block
    }

    progress,
    sub,
    sup {
      vertical-align: baseline
    }

    html {
      font-family: sans-serif;
      line-height: 1.15;
      -ms-text-size-adjust: 100%;
      -webkit-text-size-adjust: 100%
    }

    body {
      margin: 0
    }

    menu,
    article,
    aside,
    details,
    footer,
    header,
    nav,
    section {
      display: block
    }

    h1 {
      font-size: 2em;
      margin: .67em 0
    }

    figcaption,
    figure,
    main {
      display: block
    }

    figure {
      margin: 1em 40px
    }

    hr {
      box-sizing: content-box;
      height: 0
    }

    code,
    kbd,
    pre,
    samp {
      font-family: monospace, monospace;
      font-size: 1em
    }

    a {
      background-color: transparent;
      -webkit-text-decoration-skip: objects
    }

    a:active,
    a:hover {
      outline-width: 0
    }

    abbr[title] {
      border-bottom: none;
      text-decoration: underline;
      text-decoration: underline dotted
    }

    b,
    strong {
      font-weight: bolder
    }

    dfn {
      font-style: italic
    }

    mark {
      background-color: #ff0;
      color: #000
    }

    small {
      font-size: 80%
    }

    sub,
    sup {
      font-size: 75%;
      line-height: 0;
      position: relative
    }

    sub {
      bottom: -.25em
    }

    sup {
      top: -.5em
    }

    audio:not([controls]) {
      display: none;
      height: 0
    }

    img {
      border-style: none
    }

    svg:not(:root) {
      overflow: hidden
    }

    button,
    input,
    optgroup,
    select,
    textarea {
      font-family: sans-serif;
      font-size: 100%;
      line-height: 1.15;
      margin: 0
    }

    button,
    input {}

    button,
    select {
      text-transform: none
    }

    [type=submit],
    [type=reset],
    button,
    html [type=button] {
      -webkit-appearance: button
    }

    [type=button]::-moz-focus-inner,
    [type=reset]::-moz-focus-inner,
    [type=submit]::-moz-focus-inner,
    button::-moz-focus-inner {
      border-style: none;
      padding: 0
    }

    [type=button]:-moz-focusring,
    [type=reset]:-moz-focusring,
    [type=submit]:-moz-focusring,
    button:-moz-focusring {
      outline: ButtonText dotted 1px
    }

    fieldset {
      border: 1px solid silver;
      margin: 0 2px;
      padding: .35em .625em .75em
    }

    legend {
      box-sizing: border-box;
      color: inherit;
      display: table;
      max-width: 100%;
      padding: 0;
      white-space: normal
    }

    progress {}

    textarea {
      overflow: auto
    }

    [type=checkbox],
    [type=radio] {
      box-sizing: border-box;
      padding: 0
    }

    [type=number]::-webkit-inner-spin-button,
    [type=number]::-webkit-outer-spin-button {
      height: auto
    }

    [type=search] {
      -webkit-appearance: textfield;
      outline-offset: -2px
    }

    [type=search]::-webkit-search-cancel-button,
    [type=search]::-webkit-search-decoration {
      -webkit-appearance: none
    }

    ::-webkit-file-upload-button {
      -webkit-appearance: button;
      font: inherit
    }

    summary {
      display: list-item
    }

    [hidden],
    template {
      display: none
    }

    /*# sourceMappingURL=normalize.min.css.map */
  </style>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      height: 100vh;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #161616;
      color: #c5a880;
      font-family: sans-serif;
    }

    label {
      display: inline-block;
      background-color: #161616;
      padding: 16px;
      border-radius: 0.3rem;
      cursor: pointer;
      margin-top: 1rem;
      width: 300px;
      border-radius: 10px;
      border: 1px solid #c5a880;
      text-align: center;
    }

    ul {
      list-style-type: none;
      padding: 0;
      margin: 0;
    }

    .btn {
      background-color: #161616;
      border-radius: 10px;
      color: #c5a880;
      border: 1px solid #c5a880;
      padding: 16px;
      width: 300px;
      margin-bottom: 16px;
      line-height: 1.5;
      cursor: pointer;
    }

    .separator {
      font-weight: bold;
      text-align: center;
      width: 300px;
      margin: 16px 0px;
      color: #a07676;
    }

    .title {
      color: #a07676;
      font-weight: bold;
      font-size: 1.25rem;
      margin-bottom: 16px;
    }

    .text-loading {
      font-size: 2rem;
    }
  </style>

  <script>
    window.console = window.console || function (t) { };
  </script>



  <script>
    if (document.location.search.match(/type=embed/gi)) {
      window.parent.postMessage("resize", "*");
    }
  </script>


</head>

<body translate="no">
  <script src="https://cdn.jsdelivr.net/npm/three@0.115.0/build/three.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/three@0.115.0/examples/js/postprocessing/EffectComposer.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/three@0.115.0/examples/js/postprocessing/RenderPass.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/three@0.115.0/examples/js/postprocessing/ShaderPass.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/three@0.115.0/examples/js/shaders/CopyShader.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/three@0.115.0/examples/js/shaders/LuminosityHighPassShader.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/three@0.115.0/examples/js/postprocessing/UnrealBloomPass.js"></script>

  <div id="overlay">
    <ul>
      <li class="title">请选择音乐</li>
      <li>
        <button class="btn" id="btnA" type="button">
          Snowflakes Falling Down by Simon Panrucker
        </button>
      </li>
      <li><button class="btn" id="btnB" type="button">This Christmas by Dott</button></li>
      <li><button class="btn" id="btnC" type="button">No room at the inn by TRG Banks</button></li>
      <li><button class="btn" id="btnD" type="button">Jingle Bell Swing by Mark Smeby</button></li>
      <li class="separator">或者</li>
      <li>
        <input type="file" id="upload" hidden />
        <label for="upload">Upload File</label>
      </li>
    </ul>
  </div>

  <script id="rendered-js">
    const { PI, sin, cos } = Math;
    const TAU = 2 * PI;

    const map = (value, sMin, sMax, dMin, dMax) => {
      return dMin + (value - sMin) / (sMax - sMin) * (dMax - dMin);
    };

    const range = (n, m = 0) =>
      Array(n).
        fill(m).
        map((i, j) => i + j);

    const rand = (max, min = 0) => min + Math.random() * (max - min);
    const randInt = (max, min = 0) => Math.floor(min + Math.random() * (max - min));
    const randChoise = arr => arr[randInt(arr.length)];
    const polar = (ang, r = 1) => [r * cos(ang), r * sin(ang)];

    let scene, camera, renderer, analyser;
    let step = 0;
    const uniforms = {
      time: { type: "f", value: 0.0 },
      step: { type: "f", value: 0.0 }
    };

    const params = {
      exposure: 1,
      bloomStrength: 0.9,
      bloomThreshold: 0,
      bloomRadius: 0.5
    };

    let composer;

    const fftSize = 2048;
    const totalPoints = 4000;

    const listener = new THREE.AudioListener();

    const audio = new THREE.Audio(listener);

    document.querySelector("input").addEventListener("change", uploadAudio, false);

    const buttons = document.querySelectorAll(".btn");
    buttons.forEach((button, index) =>
      button.addEventListener("click", () => loadAudio(index)));


    function init() {
      const overlay = document.getElementById("overlay");
      overlay.remove();

      scene = new THREE.Scene();
      renderer = new THREE.WebGLRenderer({ antialias: true });
      renderer.setPixelRatio(window.devicePixelRatio);
      renderer.setSize(window.innerWidth, window.innerHeight);
      document.body.appendChild(renderer.domElement);

      camera = new THREE.PerspectiveCamera(
        60,
        window.innerWidth / window.innerHeight,
        1,
        1000);

      camera.position.set(-0.09397456774197047, -2.5597086635726947, 24.420789670889008);
      camera.rotation.set(0.10443543723052419, -0.003827152981119352, 0.0004011488708739715);

      const format = renderer.capabilities.isWebGL2 ?
        THREE.RedFormat :
        THREE.LuminanceFormat;

      uniforms.tAudioData = {
        value: new THREE.DataTexture(analyser.data, fftSize / 2, 1, format)
      };


      addPlane(scene, uniforms, 3000);
      addSnow(scene, uniforms);

      range(10).map(i => {
        addTree(scene, uniforms, totalPoints, [20, 0, -20 * i]);
        addTree(scene, uniforms, totalPoints, [-20, 0, -20 * i]);
      });

      const renderScene = new THREE.RenderPass(scene, camera);

      const bloomPass = new THREE.UnrealBloomPass(
        new THREE.Vector2(window.innerWidth, window.innerHeight),
        1.5,
        0.4,
        0.85);

      bloomPass.threshold = params.bloomThreshold;
      bloomPass.strength = params.bloomStrength;
      bloomPass.radius = params.bloomRadius;

      composer = new THREE.EffectComposer(renderer);
      composer.addPass(renderScene);
      composer.addPass(bloomPass);

      addListners(camera, renderer, composer);
      animate();
    }

    function animate(time) {
      analyser.getFrequencyData();
      uniforms.tAudioData.value.needsUpdate = true;
      step = (step + 1) % 1000;
      uniforms.time.value = time;
      uniforms.step.value = step;
      composer.render();
      requestAnimationFrame(animate);
    }

    function loadAudio(i) {
      document.getElementById("overlay").innerHTML =
        '<div class="text-loading">正在下载音乐，请稍等...</div>';
      const files = [
        "https://files.freemusicarchive.org/storage-freemusicarchive-org/music/no_curator/Simon_Panrucker/Happy_Christmas_You_Guys/Simon_Panrucker_-_01_-_Snowflakes_Falling_Down.mp3",
        "https://files.freemusicarchive.org/storage-freemusicarchive-org/music/no_curator/Dott/This_Christmas/Dott_-_01_-_This_Christmas.mp3",
        "https://files.freemusicarchive.org/storage-freemusicarchive-org/music/ccCommunity/TRG_Banks/TRG_Banks_Christmas_Album/TRG_Banks_-_12_-_No_room_at_the_inn.mp3",
        "https://files.freemusicarchive.org/storage-freemusicarchive-org/music/ccCommunity/Mark_Smeby/En_attendant_Nol/Mark_Smeby_-_07_-_Jingle_Bell_Swing.mp3"];

      const file = files[i];

      const loader = new THREE.AudioLoader();
      loader.load(file, function (buffer) {
        audio.setBuffer(buffer);
        audio.play();
        analyser = new THREE.AudioAnalyser(audio, fftSize);
        init();
      });




    }


    function uploadAudio(event) {
      document.getElementById("overlay").innerHTML =
        '<div class="text-loading">请稍等...</div>';
      const files = event.target.files;
      const reader = new FileReader();

      reader.onload = function (file) {
        var arrayBuffer = file.target.result;

        listener.context.decodeAudioData(arrayBuffer, function (audioBuffer) {
          audio.setBuffer(audioBuffer);
          audio.play();
          analyser = new THREE.AudioAnalyser(audio, fftSize);
          init();
        });
      };

      reader.readAsArrayBuffer(files[0]);
    }

    function addTree(scene, uniforms, totalPoints, treePosition) {
      const vertexShader = `
      attribute float mIndex;
      varying vec3 vColor;
      varying float opacity;
      uniform sampler2D tAudioData;

      float norm(float value, float min, float max ){
       return (value - min) / (max - min);
      }
      float lerp(float norm, float min, float max){
       return (max - min) * norm + min;
      }

      float map(float value, float sourceMin, float sourceMax, float destMin, float destMax){
       return lerp(norm(value, sourceMin, sourceMax), destMin, destMax);
      }


      void main() {
       vColor = color;
       vec3 p = position;
       vec4 mvPosition = modelViewMatrix * vec4( p, 1.0 );
       float amplitude = texture2D( tAudioData, vec2( mIndex, 0.1 ) ).r;
       float amplitudeClamped = clamp(amplitude-0.4,0.0, 0.6 );
       float sizeMapped = map(amplitudeClamped, 0.0, 0.6, 1.0, 20.0);
       opacity = map(mvPosition.z , -200.0, 15.0, 0.0, 1.0);
       gl_PointSize = sizeMapped * ( 100.0 / -mvPosition.z );
       gl_Position = projectionMatrix * mvPosition;
      }
      `;
      const fragmentShader = `
      varying vec3 vColor;
      varying float opacity;
      uniform sampler2D pointTexture;
      void main() {
       gl_FragColor = vec4( vColor, opacity );
       gl_FragColor = gl_FragColor * texture2D( pointTexture, gl_PointCoord ); 
      }
      `;
      const shaderMaterial = new THREE.ShaderMaterial({
        uniforms: {
          ...uniforms,
          pointTexture: {
            value: new THREE.TextureLoader().load(`https://assets.codepen.io/3685267/spark1.png`)
          }
        },


        vertexShader,
        fragmentShader,
        blending: THREE.AdditiveBlending,
        depthTest: false,
        transparent: true,
        vertexColors: true
      });


      const geometry = new THREE.BufferGeometry();
      const positions = [];
      const colors = [];
      const sizes = [];
      const phases = [];
      const mIndexs = [];

      const color = new THREE.Color();

      for (let i = 0; i < totalPoints; i++) {
        const t = Math.random();
        const y = map(t, 0, 1, -8, 10);
        const ang = map(t, 0, 1, 0, 6 * TAU) + TAU / 2 * (i % 2);
        const [z, x] = polar(ang, map(t, 0, 1, 5, 0));

        const modifier = map(t, 0, 1, 1, 0);
        positions.push(x + rand(-0.3 * modifier, 0.3 * modifier));
        positions.push(y + rand(-0.3 * modifier, 0.3 * modifier));
        positions.push(z + rand(-0.3 * modifier, 0.3 * modifier));

        color.setHSL(map(i, 0, totalPoints, 1.0, 0.0), 1.0, 0.5);

        colors.push(color.r, color.g, color.b);
        phases.push(rand(1000));
        sizes.push(1);
        const mIndex = map(i, 0, totalPoints, 1.0, 0.0);
        mIndexs.push(mIndex);
      }

      geometry.setAttribute(
        "position",
        new THREE.Float32BufferAttribute(positions, 3).setUsage(
          THREE.DynamicDrawUsage));


      geometry.setAttribute("color", new THREE.Float32BufferAttribute(colors, 3));
      geometry.setAttribute("size", new THREE.Float32BufferAttribute(sizes, 1));
      geometry.setAttribute("phase", new THREE.Float32BufferAttribute(phases, 1));
      geometry.setAttribute("mIndex", new THREE.Float32BufferAttribute(mIndexs, 1));

      const tree = new THREE.Points(geometry, shaderMaterial);

      const [px, py, pz] = treePosition;

      tree.position.x = px;
      tree.position.y = py;
      tree.position.z = pz;

      scene.add(tree);
    }

    function addSnow(scene, uniforms) {
      const vertexShader = `
      attribute float size;
      attribute float phase;
      attribute float phaseSecondary;

      varying vec3 vColor;
      varying float opacity;


      uniform float time;
      uniform float step;

      float norm(float value, float min, float max ){
       return (value - min) / (max - min);
      }
      float lerp(float norm, float min, float max){
       return (max - min) * norm + min;
      }

      float map(float value, float sourceMin, float sourceMax, float destMin, float destMax){
       return lerp(norm(value, sourceMin, sourceMax), destMin, destMax);
      }
      void main() {
       float t = time* 0.0006;

       vColor = color;

       vec3 p = position;

       p.y = map(mod(phase+step, 1000.0), 0.0, 1000.0, 25.0, -8.0);

       p.x += sin(t+phase);
       p.z += sin(t+phaseSecondary);

       opacity = map(p.z, -150.0, 15.0, 0.0, 1.0);

       vec4 mvPosition = modelViewMatrix * vec4( p, 1.0 );

       gl_PointSize = size * ( 100.0 / -mvPosition.z );

       gl_Position = projectionMatrix * mvPosition;

      }
      `;

      const fragmentShader = `
      uniform sampler2D pointTexture;
      varying vec3 vColor;
      varying float opacity;

      void main() {
       gl_FragColor = vec4( vColor, opacity );
       gl_FragColor = gl_FragColor * texture2D( pointTexture, gl_PointCoord ); 
      }
      `;
      function createSnowSet(sprite) {
        const totalPoints = 300;
        const shaderMaterial = new THREE.ShaderMaterial({
          uniforms: {
            ...uniforms,
            pointTexture: {
              value: new THREE.TextureLoader().load(sprite)
            }
          },


          vertexShader,
          fragmentShader,
          blending: THREE.AdditiveBlending,
          depthTest: false,
          transparent: true,
          vertexColors: true
        });


        const geometry = new THREE.BufferGeometry();
        const positions = [];
        const colors = [];
        const sizes = [];
        const phases = [];
        const phaseSecondaries = [];

        const color = new THREE.Color();

        for (let i = 0; i < totalPoints; i++) {
          const [x, y, z] = [rand(25, -25), 0, rand(15, -150)];
          positions.push(x);
          positions.push(y);
          positions.push(z);

          color.set(randChoise(["#f1d4d4", "#f1f6f9", "#eeeeee", "#f1f1e8"]));

          colors.push(color.r, color.g, color.b);
          phases.push(rand(1000));
          phaseSecondaries.push(rand(1000));
          sizes.push(rand(4, 2));
        }

        geometry.setAttribute(
          "position",
          new THREE.Float32BufferAttribute(positions, 3));

        geometry.setAttribute("color", new THREE.Float32BufferAttribute(colors, 3));
        geometry.setAttribute("size", new THREE.Float32BufferAttribute(sizes, 1));
        geometry.setAttribute("phase", new THREE.Float32BufferAttribute(phases, 1));
        geometry.setAttribute(
          "phaseSecondary",
          new THREE.Float32BufferAttribute(phaseSecondaries, 1));


        const mesh = new THREE.Points(geometry, shaderMaterial);

        scene.add(mesh);
      }
      const sprites = [
        "https://assets.codepen.io/3685267/snowflake1.png",
        "https://assets.codepen.io/3685267/snowflake2.png",
        "https://assets.codepen.io/3685267/snowflake3.png",
        "https://assets.codepen.io/3685267/snowflake4.png",
        "https://assets.codepen.io/3685267/snowflake5.png"];

      sprites.forEach(sprite => {
        createSnowSet(sprite);
      });
    }

    function addPlane(scene, uniforms, totalPoints) {
      const vertexShader = `
      attribute float size;
      attribute vec3 customColor;
      varying vec3 vColor;

      void main() {
       vColor = customColor;
       vec4 mvPosition = modelViewMatrix * vec4( position, 1.0 );
       gl_PointSize = size * ( 300.0 / -mvPosition.z );
       gl_Position = projectionMatrix * mvPosition;

      }
      `;
      const fragmentShader = `
      uniform vec3 color;
      uniform sampler2D pointTexture;
      varying vec3 vColor;

      void main() {
       gl_FragColor = vec4( vColor, 1.0 );
       gl_FragColor = gl_FragColor * texture2D( pointTexture, gl_PointCoord );

      }
      `;
      const shaderMaterial = new THREE.ShaderMaterial({
        uniforms: {
          ...uniforms,
          pointTexture: {
            value: new THREE.TextureLoader().load(`https://assets.codepen.io/3685267/spark1.png`)
          }
        },


        vertexShader,
        fragmentShader,
        blending: THREE.AdditiveBlending,
        depthTest: false,
        transparent: true,
        vertexColors: true
      });


      const geometry = new THREE.BufferGeometry();
      const positions = [];
      const colors = [];
      const sizes = [];

      const color = new THREE.Color();

      for (let i = 0; i < totalPoints; i++) {
        const [x, y, z] = [rand(-25, 25), 0, rand(-150, 15)];
        positions.push(x);
        positions.push(y);
        positions.push(z);

        color.set(randChoise(["#93abd3", "#f2f4c0", "#9ddfd3"]));

        colors.push(color.r, color.g, color.b);
        sizes.push(1);
      }

      geometry.setAttribute(
        "position",
        new THREE.Float32BufferAttribute(positions, 3).setUsage(
          THREE.DynamicDrawUsage));


      geometry.setAttribute(
        "customColor",
        new THREE.Float32BufferAttribute(colors, 3));

      geometry.setAttribute("size", new THREE.Float32BufferAttribute(sizes, 1));

      const plane = new THREE.Points(geometry, shaderMaterial);

      plane.position.y = -8;
      scene.add(plane);
    }

    function addListners(camera, renderer, composer) {
      document.addEventListener("keydown", e => {
        const { x, y, z } = camera.position;
        console.log(`camera.position.set(${x},${y},${z})`);
        const { x: a, y: b, z: c } = camera.rotation;
        console.log(`camera.rotation.set(${a},${b},${c})`);
      });

      window.addEventListener(
        "resize",
        () => {
          const width = window.innerWidth;
          const height = window.innerHeight;

          camera.aspect = width / height;
          camera.updateProjectionMatrix();

          renderer.setSize(width, height);
          composer.setSize(width, height);
        },
        false);

    }
  </script>

</body>

</html>