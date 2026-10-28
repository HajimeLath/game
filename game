<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Contra el Bloqueo — Votación en la ONU</title>
<style>
  *{box-sizing:border-box;margin:0;padding:0}
  body{
    font-family:'Segoe UI',system-ui,-apple-system,sans-serif;
    background:radial-gradient(circle at 50% 0%,#16324f 0%,#0a1622 70%);
    color:#e9eef5;min-height:100vh;
    display:flex;align-items:center;justify-content:center;padding:16px;
  }
  .oculto{display:none !important}
  .pantalla{width:100%;max-width:1080px}

  /* ---------- INICIO ---------- */
  .tarjeta-inicio,.tarjeta-final{
    background:linear-gradient(160deg,rgba(255,255,255,.07),rgba(255,255,255,.02));
    border:1px solid rgba(255,255,255,.14);border-radius:22px;
    padding:38px 32px;text-align:center;backdrop-filter:blur(6px);
    box-shadow:0 24px 60px rgba(0,0,0,.5);
  }
  .bandera-onu{font-size:52px;line-height:1}
  h1{font-size:2rem;margin:14px 0 6px;letter-spacing:.5px;
     background:linear-gradient(90deg,#7fd0ff,#c9e7ff);-webkit-background-clip:text;
     background-clip:text;color:transparent}
  .sub{color:#8fb4d1;font-size:.92rem;margin-bottom:18px;letter-spacing:.4px}
  .desc{color:#c2d3e2;font-size:.95rem;line-height:1.6;max-width:640px;margin:0 auto 26px}
  .desc b{color:#7fd0ff}
  .btn-grande{
    background:linear-gradient(135deg,#2f8fd8,#1c5f9e);color:#fff;border:none;
    padding:15px 34px;border-radius:12px;font-size:1rem;font-weight:600;
    cursor:pointer;letter-spacing:.4px;transition:.2s;
    box-shadow:0 10px 24px rgba(47,143,216,.35);
  }
  .btn-grande:hover{transform:translateY(-2px);box-shadow:0 14px 30px rgba(47,143,216,.5)}

  /* ---------- JUEGO ---------- */
  .juego-grid{display:grid;grid-template-columns:340px 1fr;gap:20px}
  @media(max-width:860px){.juego-grid{grid-template-columns:1fr}}

  .col-izq{
    background:linear-gradient(170deg,rgba(255,255,255,.06),rgba(255,255,255,.015));
    border:1px solid rgba(255,255,255,.12);border-radius:20px;padding:18px;
  }
  .col-der{
    background:linear-gradient(170deg,rgba(255,255,255,.06),rgba(255,255,255,.015));
    border:1px solid rgba(255,255,255,.12);border-radius:20px;padding:22px;
    display:flex;flex-direction:column;
  }

  /* medidor */
  .medidor{margin-bottom:14px;position:relative}
  .medidor-top{display:flex;justify-content:space-between;font-size:.78rem;
    color:#9fc0d8;letter-spacing:.6px;text-transform:uppercase;margin-bottom:6px}
  #puntosTxt{font-weight:700;color:#7fd0ff;font-size:.95rem}
  .barra{height:12px;background:rgba(255,255,255,.1);border-radius:99px;overflow:hidden}
  .barra-fill{height:100%;width:50%;border-radius:99px;
    background:linear-gradient(90deg,#f2b544,#4ad991);
    transition:width .6s cubic-bezier(.3,1.4,.5,1), background .6s}
  .delta{
    position:absolute;right:0;top:-6px;font-weight:800;font-size:1.25rem;
    opacity:0;pointer-events:none;
  }
  .delta.animar{animation:subir 1.4s ease-out forwards}
  .delta.pos{color:#4ad991}
  .delta.neg{color:#ff6b6b}
  @keyframes subir{
    0%{opacity:0;transform:translateY(10px) scale(.7)}
    25%{opacity:1;transform:translateY(-8px) scale(1.15)}
    100%{opacity:0;transform:translateY(-34px) scale(1)}
  }

  .retrato{width:100%;max-width:260px;margin:0 auto;display:block}
  .retrato svg{width:100%;height:auto;display:block;
    filter:drop-shadow(0 12px 22px rgba(0,0,0,.45))}
  .nombre{text-align:center;font-size:.75rem;letter-spacing:1.2px;
    text-transform:uppercase;color:#8fb4d1;margin:6px 0 12px}

  .burbuja{
    background:rgba(255,255,255,.09);border:1px solid rgba(255,255,255,.16);
    border-radius:16px;padding:14px 16px;font-size:.9rem;line-height:1.5;
    color:#e6f0fa;position:relative;min-height:70px;
  }
  .burbuja::before{
    content:'';position:absolute;top:-9px;left:28px;width:16px;height:16px;
    background:rgba(255,255,255,.09);border-left:1px solid rgba(255,255,255,.16);
    border-top:1px solid rgba(255,255,255,.16);transform:rotate(45deg);
  }
  .narracion{margin-top:10px;font-size:.82rem;font-style:italic;color:#9fc0d8;
    line-height:1.45;min-height:18px}

  /* panel derecho */
  .etiqueta{font-size:.72rem;letter-spacing:1.4px;text-transform:uppercase;
    color:#f2b544;margin-bottom:8px;font-weight:700}
  #temaRonda{font-size:1.08rem;line-height:1.4;margin-bottom:16px;color:#dbeaf7}
  .opciones{display:flex;flex-direction:column;gap:10px;overflow-y:auto;
    max-height:52vh;padding-right:6px;margin-bottom:16px}
  .opciones::-webkit-scrollbar{width:6px}
  .opciones::-webkit-scrollbar-thumb{background:rgba(255,255,255,.2);border-radius:9px}

  .opcion{
    display:flex;gap:12px;align-items:flex-start;width:100%;text-align:left;
    background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.12);
    border-radius:13px;padding:13px 15px;color:#e9eef5;font-size:.9rem;
    line-height:1.45;cursor:pointer;transition:.18s;font-family:inherit;
  }
  .opcion:hover:not(:disabled){background:rgba(64,145,220,.2);
    border-color:#4a9fdc;transform:translateX(5px)}
  .opcion:disabled{opacity:.4;cursor:default}
  .opcion .num{
    flex:0 0 24px;height:24px;border-radius:50%;background:rgba(127,208,255,.18);
    color:#7fd0ff;font-weight:800;font-size:.78rem;display:flex;
    align-items:center;justify-content:center;margin-top:1px;
  }
  #btnContinuar{align-self:flex-end}

  /* ---------- FINAL ---------- */
  .votos{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin:26px 0}
  @media(max-width:620px){.votos{grid-template-columns:1fr}}
  .voto{border-radius:16px;padding:20px 12px;border:1px solid rgba(255,255,255,.14);
    background:rgba(255,255,255,.04)}
  .voto .numVoto{font-size:2.5rem;font-weight:800;line-height:1}
  .voto .lbl{font-size:.74rem;letter-spacing:.8px;text-transform:uppercase;
    color:#9fc0d8;margin-top:8px}
  .a-favor{border-color:rgba(74,217,145,.45);background:rgba(74,217,145,.09)}
  .a-favor .numVoto{color:#4ad991}
  .en-contra{border-color:rgba(255,107,107,.45);background:rgba(255,107,107,.09)}
  .en-contra .numVoto{color:#ff6b6b}
  .abst .numVoto{color:#f2b544}
  .retrato-final{width:170px;margin:0 auto 16px}
  .retrato-final svg{width:100%;height:auto;display:block;
    filter:drop-shadow(0 10px 20px rgba(0,0,0,.45))}
  .mensaje{color:#c2d3e2;line-height:1.6;font-size:.95rem;max-width:640px;
    margin:0 auto 26px}
</style>
</head>
<body>

<!-- ================= INICIO ================= -->
<section id="inicio" class="pantalla">
  <div class="tarjeta-inicio">
    <div class="bandera-onu">🇨🇺</div>
    <h1>Contra el Bloqueo</h1>
    <p class="sub">Asamblea General de la ONU · Resolución contra el bloqueo a Cuba</p>
    <p class="desc">
      Eres el Canciller de Cuba. Deberás enfrentar al <b>Secretario de Estado de los Estados Unidos</b>
      en dos rondas de debate: primero <b>él ataca y tú respondes</b>; después
      <b>tú atacas y él se defiende</b>. Cada argumento mejora o empeora la opinión
      de los demás países... y de esa opinión depende el voto final.
      <br><br>
      <b>Cada partida es diferente:</b> el Secretario de Estado elige 5 de sus 15 argumentos al azar,
      y las opciones aparecen desordenadas para que no puedas identificar a simple vista la mejor.
    </p>
    <button class="btn-grande" onclick="iniciarJuego()">Comenzar debate</button>
  </div>
</section>

<!-- ================= JUEGO ================= -->
<section id="juego" class="pantalla oculto">
  <div class="juego-grid">
    <aside class="col-izq">
      <div class="medidor">
        <div class="medidor-top"><span>Apoyo internacional</span><span id="puntosTxt">50</span></div>
        <div class="barra"><div id="barraFill" class="barra-fill"></div></div>
        <div id="delta" class="delta"></div>
      </div>

      <div id="caraContenedor" class="retrato">
        <!-- ====== CARA DEL SECRETARIO DE ESTADO ====== -->
        <svg id="canciller" viewBox="0 0 300 320" xmlns="http://www.w3.org/2000/svg">
          <circle cx="150" cy="150" r="142" fill="#eef3f8"/>
          <!-- hombros / traje -->
          <path d="M30 320 Q38 244 108 226 L192 226 Q262 244 270 320 Z" fill="#1b2a41"/>
          <!-- camisa -->
          <path d="M120 230 L150 278 L180 230 L166 224 L134 224 Z" fill="#ffffff"/>
          <!-- corbata -->
          <path d="M150 250 L141 268 L150 302 L159 268 Z" fill="#c1121f"/>
          <!-- cuello -->
          <rect x="128" y="200" width="44" height="38" rx="12" fill="#e0a97f"/>
          <!-- orejas -->
          <ellipse cx="72" cy="152" rx="14" ry="20" fill="#e8b48f"/>
          <ellipse cx="228" cy="152" rx="14" ry="20" fill="#e8b48f"/>
          <!-- cara -->
          <ellipse id="cara" cx="150" cy="145" rx="78" ry="88" fill="#f3c9a6"/>
          <!-- rubor -->
          <ellipse id="rubor" cx="104" cy="176" rx="16" ry="10" fill="#f08b7a" opacity="0"/>
          <ellipse id="rubor2" cx="196" cy="176" rx="16" ry="10" fill="#f08b7a" opacity="0"/>
          <!-- pelo -->
          <path id="pelo" d="M72 132 Q66 52 150 46 Q234 52 228 132 Q216 84 150 80 Q84 84 72 132 Z" fill="#d9c07a"/>
          <!-- ojos -->
          <ellipse id="ojoL" cx="120" cy="140" rx="17" ry="12" fill="#ffffff"/>
          <ellipse id="ojoR" cx="180" cy="140" rx="17" ry="12" fill="#ffffff"/>
          <circle id="pupL" cx="120" cy="141" r="7" fill="#1b2a41"/>
          <circle id="pupR" cx="180" cy="141" r="7" fill="#1b2a41"/>
          <!-- cejas -->
          <path id="cejaL" d="M96 110 L140 106" stroke="#6b4f1d" stroke-width="7"
                stroke-linecap="round" fill="none"/>
          <path id="cejaR" d="M204 110 L160 106" stroke="#6b4f1d" stroke-width="7"
                stroke-linecap="round" fill="none"/>
          <!-- nariz -->
          <path d="M150 146 Q141 168 152 172" stroke="#d9a179" stroke-width="5"
                fill="none" stroke-linecap="round"/>
          <!-- boca -->
          <path id="boca" d="M116 190 Q150 204 184 190" stroke="#a4453b"
                stroke-width="6" fill="none" stroke-linecap="round"/>
          <!-- sudor -->
          <path id="sudor" d="M228 92 q-9 15 0 21 q9 -6 0 -21" fill="#6ec6f5" opacity="0"/>
          <path id="sudor2" d="M72 100 q-8 13 0 18 q8 -5 0 -18" fill="#6ec6f5" opacity="0"/>
        </svg>
      </div>
      <div class="nombre">Secretario de Estado de los Estados Unidos</div>
      <div class="burbuja" id="burbuja"></div>
      <div class="narracion" id="narracion"></div>
    </aside>

    <main class="col-der">
      <div class="etiqueta" id="etiquetaFase"></div>
      <h2 id="temaRonda"></h2>
      <div class="opciones" id="opciones"></div>
      <button id="btnContinuar" class="btn-grande oculto" onclick="continuar()">Continuar →</button>
    </main>
  </div>
</section>

<!-- ================= FINAL ================= -->
<section id="final" class="pantalla oculto">
  <div class="tarjeta-final">
    <h1 id="tituloFinal"></h1>
    <p class="sub">Resultado de la votación · 193 países miembros</p>
    <div class="votos">
      <div class="voto a-favor">
        <div class="numVoto" id="vFavor">0</div>
        <div class="lbl">A favor de tumbar el bloqueo</div>
      </div>
      <div class="voto en-contra">
        <div class="numVoto" id="vContra">0</div>
        <div class="lbl">En contra</div>
      </div>
      <div class="voto abst">
        <div class="numVoto" id="vAbst">0</div>
        <div class="lbl">Abstenciones</div>
      </div>
    </div>
    <div id="caraFinal" class="retrato-final"></div>
    <p id="mensajeFinal" class="mensaje"></p>
    <button class="btn-grande" onclick="iniciarJuego()">Jugar de nuevo</button>
  </div>
</section>

<script>
/* =========================================================
   UTILIDADES
   ========================================================= */
function shuffle(arr){
  const a = [...arr];
  for (let i = a.length - 1; i > 0; i--){
    const j = Math.floor(Math.random() * (i + 1));
    [a[i], a[j]] = [a[j], a[i]];
  }
  return a;
}
function elegirAleatorios(arr, n){
  return shuffle(arr).slice(0, n);
}

/* =========================================================
   FASE 1: EL SECRETARIO DE ESTADO ATACA — TÚ RESPONDES
   (15 ataques; se eligen 5 al azar por partida)
   ========================================================= */
const FASE1 = [
  {
    ataque: "El bloqueo es un asunto bilateral entre Estados Unidos y Cuba. La comunidad internacional no tiene por qué inmiscuirse en decisiones soberanas de dos países.",
    opciones: [
      { t: "Precisamente porque es bilateral, no puede aplicarse fuera de sus fronteras: la Ley Helms-Burton sanciona a empresas de terceros países y viola la soberanía de más de 40 naciones. Por eso 187 países lo condenan cada año en la ONU.", d: 12 },
      { t: "Respetamos su soberanía, pero le pedimos la misma reciprocidad: permita que Cuba comercie libremente con el resto del mundo.", d: 7 },
      { t: "La Asamblea General lo ha condenado 32 veces consecutivas. Si fuera un asunto privado, ¿por qué preocupa a casi todo el planeta?", d: 5 },
      { t: "Ningún país es una isla: lo que pasa en Cuba afecta a toda la región.", d: 1 },
      { t: "Ese argumento es tan viejo como el bloqueo. Búsquense otro.", d: -11 }
    ]
  },
  {
    ataque: "El bloqueo responde a la situación de los derechos humanos en Cuba. Mientras no haya elecciones libres ni libertad de prensa, las sanciones continuarán.",
    opciones: [
      { t: "Cuba ha ratificado 44 tratados internacionales de derechos humanos y coopera con los mecanismos de la ONU. El bloqueo, en cambio, viola el derecho a la salud y a la alimentación de 11 millones de personas: las sanciones colectivas están prohibidas por la Carta de la ONU.", d: 12 },
      { t: "Cuba tiene un sistema electoral participativo y una Constitución aprobada en referendo. Invitamos a observadores independientes a verificarlo.", d: 7 },
      { t: "Los derechos humanos no se miden con un solo rasero, ni con sanciones que castigan al pueblo entero.", d: 4 },
      { t: "Estados Unidos encarcela a más personas que cualquier otro país del mundo.", d: -6 },
      { t: "¿Derechos humanos? Pregúntenle a los muertos de Irak.", d: -12 }
    ]
  },
  {
    ataque: "Cuba es un riesgo para la seguridad regional: mantiene vínculos militares con países hostiles a Estados Unidos y sirve de plataforma en el Caribe.",
    opciones: [
      { t: "Cuba no tiene bases militares en el exterior ni armas de destrucción masiva. Estados Unidos, en cambio, ocupa Guantánamo contra la voluntad cubana desde 1903 y mantiene más de 800 bases en 80 países. Nuestra cooperación es médica: más de 400.000 profesionales de la salud han servido en 160 naciones.", d: 12 },
      { t: "Cuba es un país pequeño que ha sufrido invasiones, sabotajes y más de 600 planes de magnicidio documentados. Nuestra respuesta ha sido solidaridad, no agresión.", d: 7 },
      { t: "Nuestras alianzas son soberanas y no amenazan a nadie.", d: 3 },
      { t: "Ustedes financian golpes de Estado en toda América Latina.", d: -7 },
      { t: "El país con más guerras del planeta no tiene autoridad para hablar de seguridad.", d: -12 }
    ]
  },
  {
    ataque: "Las sanciones son selectivas: existen licencias y excepciones para alimentos y medicinas. El bloqueo no afecta la ayuda humanitaria.",
    opciones: [
      { t: "Las excepciones existen en el papel, pero ningún banco ni naviera se arriesga a multas millonarias por operar con Cuba. El bloqueo costó más de 5.000 millones de dólares en un solo año y provocó desabastecimiento de medicamentos oncológicos. Una excepción que depende de un permiso no es una excepción: es una condición.", d: 12 },
      { t: "Las licencias son tan complejas y lentas que en la práctica resultan inoperantes. Los proveedores prefieren no vender antes que arriesgarse.", d: 7 },
      { t: "Si realmente existen esas excepciones, levante el bloqueo y demuéstrelo.", d: 4 },
      { t: "Las excepciones no alimentan a nadie.", d: 1 },
      { t: "Eso es una mentira más de su propaganda.", d: -10 }
    ]
  },
  {
    ataque: "Si Cuba quiere que se levante el bloqueo, debe avanzar hacia la democracia y el libre mercado. El bloqueo es una herramienta de presión legítima, no un castigo.",
    opciones: [
      { t: "El bloqueo no presiona a un gobierno: castiga a un pueblo entero desde hace más de 60 años sin lograr su objetivo. La ONU lo ha rechazado 32 veces. Cuba ha reformado su economía y abierto la inversión extranjera por decisión soberana; lo que no aceptaremos nunca es un cambio impuesto desde Washington.", d: 12 },
      { t: "Cuba ha actualizado su modelo económico, reconoce la propiedad privada y fomenta la inversión extranjera. Lo que pedimos es reciprocidad, no tutela.", d: 7 },
      { t: "Las reformas las decidimos los cubanos, no el Departamento de Estado.", d: 5 },
      { t: "El libre mercado ha arruinado a media América Latina.", d: -5 },
      { t: "Guárdense su democracia de bombardeos.", d: -12 }
    ]
  },
  {
    ataque: "Cuba figura en la lista de países patrocinadores del terrorismo del Departamento de Estado. Eso justifica medidas adicionales.",
    opciones: [
      { t: "Cuba fue incluida en 2021 por razones políticas: Colombia, país afectado por el conflicto, ha pedido su exclusión. Cuba ha sido víctima de terrorismo: 3.478 muertos y más de 2.000 discapacitados por atentados financiados desde el exterior, incluido el del avión cubano en 1976 con 73 víctimas. Es una designación política, no técnica.", d: 12 },
      { t: "Cuba coopera con Estados Unidos en la lucha antiterrorista y ha sido víctima de terrorismo durante décadas.", d: 7 },
      { t: "La designación es unilateral y no cuenta con el respaldo de la comunidad internacional.", d: 5 },
      { t: "Cuba no patrocina terrorismo; es un país pequeño y pacífico.", d: 1 },
      { t: "Esa lista es una broma de mal gusto.", d: -10 }
    ]
  },
  {
    ataque: "Cuba alberga fugitivos de la justicia estadounidense, incluidos autores de crímenes violentos de los años setenta.",
    opciones: [
      { t: "Cuba ha devuelto a Estados Unidos a decenas de fugitivos y ha solicitado la extradición de más de 70 terroristas, entre ellos Luis Posada Carriles, al que Estados Unidos ha protegido. La cooperación judicial debe ser recíproca, no unilateral.", d: 12 },
      { t: "Cuba tiene acuerdos de extradición y ha cooperado pese a las diferencias políticas.", d: 7 },
      { t: "Si de verdad les preocupa la justicia, entreguen a Posada Carriles.", d: 4 },
      { t: "Hablemos de los criminales que ustedes protegen.", d: -3 },
      { t: "No somos su basurero judicial.", d: -10 }
    ]
  },
  {
    ataque: "En Cuba hay presos políticos. Por eso mantenemos las sanciones.",
    opciones: [
      { t: "Cuba ha otorgado amnistías e indultos y tiene un sistema legal que procesa a quienes violan la ley, no por sus ideas. Estados Unidos, por su parte, tiene la mayor población carcelaria del mundo y mantiene a decenas de detenidos en Guantánamo sin cargos ni juicios.", d: 12 },
      { t: "Cuba ha liberado a cientos de personas y coopera con organismos de derechos humanos.", d: 7 },
      { t: "Ningún país está libre de críticas en materia de derechos humanos.", d: 4 },
      { t: "Guantánamo está en Cuba y no respeta el debido proceso.", d: 2 },
      { t: "Eso es pura propaganda.", d: -8 }
    ]
  },
  {
    ataque: "El bloqueo es una compensación por las propiedades expropiadas a ciudadanos estadounidenses. Cuba debe pagar.",
    opciones: [
      { t: "Cuba ha ofrecido negociar y ha pagado compensaciones a otros países. El problema es que Estados Unidos exige el pago previo a cualquier diálogo, mientras el bloqueo impide generar los recursos para hacerlo. Es una pescadilla que se muerde la cola.", d: 12 },
      { t: "Cuba ha mostrado voluntad de negociar compensaciones en igualdad de condiciones.", d: 7 },
      { t: "Las expropiaciones fueron parte de una reforma agraria legítima y ya se han resuelto con otros países.", d: 5 },
      { t: "La deuda histórica es mutua.", d: 2 },
      { t: "Expropiar fue nuestro derecho soberano.", d: -4 }
    ]
  },
  {
    ataque: "Cuba apoya al régimen venezolano e interfiere en la región. Por eso debemos mantener la presión.",
    opciones: [
      { t: "Cuba mantiene relaciones de cooperación con Venezuela, un país soberano, como las mantiene con 190 naciones. Cuba no tiene bases militares en el exterior y no ha invadido a nadie. Estados Unidos, en cambio, ha sancionado a Venezuela, Nicaragua y Cuba al mismo tiempo, y ha intentado cambiar gobiernos por la fuerza.", d: 12 },
      { t: "La cooperación cubana con Venezuela es médica y educativa, no militar.", d: 7 },
      { t: "Cada país decide sus alianzas soberanamente.", d: 5 },
      { t: "No hablen de injerencia cuando ustedes son los reyes.", d: -4 },
      { t: "Venezuela no es su colonia.", d: -10 }
    ]
  },
  {
    ataque: "Las misiones médicas cubanas son una forma de trata de personas. Los médicos son obligados a trabajar en el exterior.",
    opciones: [
      { t: "Más de 400.000 profesionales cubanos de la salud han servido en 160 países, y hay 30.000 actualmente en misión. Han salvado millones de vidas, incluidos pacientes en África y América Latina. Cuba ha invitado a la OMS y a la OIT a verificar el programa. Ningún país ha presentado pruebas de trata.", d: 12 },
      { t: "Esos programas son voluntarios y han sido reconocidos por la OMS y la OPS.", d: 7 },
      { t: "Los médicos cubanos son héroes, no víctimas de trata.", d: 5 },
      { t: "Donde no llega un médico cubano, no llega nadie.", d: 2 },
      { t: "Eso es una calumnia contra nuestros médicos.", d: -8 }
    ]
  },
  {
    ataque: "Estados Unidos ha ofrecido ayuda humanitaria y Cuba la rechaza. Eso es un hecho.",
    opciones: [
      { t: "Cuba ha aceptado ayuda humanitaria de muchos países, incluidos donantes estadounidenses. Lo que rechaza es una ayuda condicionada políticamente y la imposibilidad de comprar insumos por el bloqueo. Estados Unidos ha bloqueado incluso donaciones de terceros a Cuba.", d: 12 },
      { t: "Cuba ha aceptado ayuda de la Cruz Roja, de la ONU y de países europeos.", d: 7 },
      { t: "Si la ayuda es sincera, que se levante el bloqueo y se permita comprar medicinas.", d: 5 },
      { t: "No necesitamos limosnas condicionadas.", d: -3 },
      { t: "Guárdense su ayuda.", d: -9 }
    ]
  },
  {
    ataque: "Lo que ustedes llaman bloqueo es en realidad un embargo. El comercio normal está permitido bajo licencia.",
    opciones: [
      { t: "Un bloqueo que dura 60 años y que ha sido condenado 32 veces por la ONU no es un simple embargo. Las licencias son tan complejas que ningún banco ni naviera las usa: el resultado práctico es que Cuba no puede comprar alimentos ni medicinas. La diferencia entre 'embargo' y 'bloqueo' es semántica; el efecto es el mismo.", d: 12 },
      { t: "Las licencias existen en el papel, pero en la práctica no funcionan por el miedo a represalias.", d: 7 },
      { t: "Llámenlo como quieran: los cubanos sufren igual.", d: 4 },
      { t: "Es un bloqueo con otro nombre.", d: 2 },
      { t: "Eso es jugar con las palabras.", d: -3 }
    ]
  },
  {
    ataque: "Cuba restringe el acceso a internet y la libertad de expresión. Por eso continúa el bloqueo.",
    opciones: [
      { t: "Cuba ha expandido el acceso a internet en los últimos años y tiene más de 7 millones de usuarios. Las restricciones responden en parte al bloqueo, que impide comprar equipos y servicios. Estados Unidos, por su parte, ha usado las plataformas para intentar desestabilizar el país.", d: 12 },
      { t: "Cuba ha ampliado la conectividad y reconoce la libertad de expresión en su Constitución.", d: 7 },
      { t: "Ningún país es perfecto en libertad de prensa.", d: 4 },
      { t: "El bloqueo también limita el acceso a la tecnología.", d: 2 },
      { t: "Eso es una excusa.", d: -6 }
    ]
  },
  {
    ataque: "Si Cuba está tan afectada por el bloqueo, ¿por qué gasta en misiones internacionales en lugar de atender a su propio pueblo?",
    opciones: [
      { t: "La solidaridad es parte de la identidad cubana y también una fuente de ingresos: las misiones médicas generan divisas que financian servicios sociales. Cuba ha enviado médicos a Italia durante la pandemia y a África durante el ébola. La pregunta debería ser por qué Estados Unidos bloquea los recursos que Cuba necesita.", d: 12 },
      { t: "La cooperación internacional es voluntaria y ha salvado vidas.", d: 7 },
      { t: "Cuba prioriza la salud y la educación de su pueblo: tiene la tasa de médicos por habitante más alta del mundo.", d: 5 },
      { t: "Solidaridad no es un lujo.", d: 2 },
      { t: "No nos den lecciones de prioridades.", d: -4 }
    ]
  }
];

/* =========================================================
   FASE 2: TÚ ATACAS — EL SECRETARIO DE ESTADO SE DEFIENDE
   (15 temas; se eligen 5 al azar por partida)
   ========================================================= */
const FASE2 = [
  {
    tema: "El costo humano del bloqueo",
    opciones: [
      { t: "El bloqueo ha costado a Cuba más de 150.000 millones de dólares en seis décadas y es la causa principal de la escasez de medicinas y alimentos. ¿Cómo justifica su gobierno el sufrimiento de niños y ancianos?",
        defensa: "Las sanciones no prohíben medicinas ni alimentos. Existen licencias humanitarias para eso.", d: 12 },
      { t: "El bloqueo viola la Carta de la ONU y el derecho internacional humanitario: es una medida coercitiva unilateral que castiga a la población civil.",
        defensa: "Es una medida política bilateral, no un acto de guerra. No hay violación del derecho internacional.", d: 8 },
      { t: "Cuba importa alimentos y medicinas, y el bloqueo encarece cada operación con intermediarios y fletes. El costo lo pagan los cubanos.",
        defensa: "Las empresas cubanas pueden comprar en terceros países sin problema alguno.", d: 5 },
      { t: "El bloqueo es una medida fracasada que no ha logrado nada en 60 años.",
        defensa: "Ha logrado mantener la presión por los derechos humanos.", d: 1 },
      { t: "Su país es un imperio criminal que solo sabe de guerras.",
        defensa: "Con insultos no se construye nada; esta es la razón por la que no hay diálogo.", d: -9 }
    ]
  },
  {
    tema: "La extraterritorialidad de la Ley Helms-Burton",
    opciones: [
      { t: "La Ley Helms-Burton sanciona a empresas de terceros países que comercian con Cuba. ¿Con qué derecho impone su legislación a naciones soberanas? La Unión Europea activó su bloqueo estatutario y la OMC falló contra ustedes.",
        defensa: "La ley protege propiedades estadounidenses reclamadas; es una cuestión de derechos de propiedad.", d: 12 },
      { t: "La extraterritorialidad viola la soberanía de más de 40 países y el principio de no intervención.",
        defensa: "No intervenimos: solo regulamos a nuestras empresas y a quienes se benefician de bienes expropiados.", d: 8 },
      { t: "Los bancos europeos y asiáticos han sido multados por operar con Cuba. ¿No es eso abuso de poder?",
        defensa: "Son acuerdos de cumplimiento con entidades que violaron nuestras leyes.", d: 4 },
      { t: "Ningún país acepta su ley fuera de sus fronteras.",
        defensa: "Muchos países cooperan con nosotros en materia de sanciones.", d: 2 },
      { t: "Ustedes creen que el mundo es su patio trasero.",
        defensa: "Ese tono no ayuda al diálogo, señor canciller.", d: -5 }
    ]
  },
  {
    tema: "El aislamiento diplomático",
    opciones: [
      { t: "En la última votación, 187 países pidieron el fin del bloqueo y solo 2 lo defendieron. ¿No es hora de escuchar a la comunidad internacional?",
        defensa: "La Asamblea General no decide nuestra política exterior; la defendemos porque creemos en ella.", d: 12 },
      { t: "El mundo entero, del Sur global a sus propios aliados, considera el bloqueo una medida anacrónica.",
        defensa: "Nuestros aliados entienden nuestra posición de seguridad.", d: 8 },
      { t: "La resolución contra el bloqueo ha recibido más votos que cualquier otra en la historia de la ONU.",
        defensa: "Los votos no cambian los hechos sobre el terreno.", d: 5 },
      { t: "Están cada vez más solos.",
        defensa: "Tenemos decenas de países socios que nos apoyan.", d: 1 },
      { t: "Nadie quiere a Estados Unidos en el mundo.",
        defensa: "Ese exabrupto confirma que no hay argumentos serios de su parte.", d: -8 }
    ]
  },
  {
    tema: "La doble moral y la base de Guantánamo",
    opciones: [
      { t: "Estados Unidos bombardeó Irak y Libia con base en mentiras y mantiene la prisión de Guantánamo, en territorio cubano ocupado, sin juicios ni garantías. ¿Con qué autoridad moral sanciona a Cuba por derechos humanos?",
        defensa: "Guantánamo es un asunto de seguridad nacional y nuestro historial de derechos humanos es sólido.", d: 12 },
      { t: "Guantánamo es una violación flagrante del derecho internacional y de la soberanía cubana. Cuba exige su devolución desde hace más de 60 años.",
        defensa: "El arrendamiento es un tratado vigente de 1903.", d: 9 },
      { t: "Cuba ha denunciado la base ilegal y las violaciones de derechos humanos que allí ocurren.",
        defensa: "Es una base legítima, reconocida por acuerdos históricos.", d: 5 },
      { t: "Primero limpien su propia casa.",
        defensa: "Preferiría que habláramos de hechos, no de consignas.", d: 2 },
      { t: "Son los mayores violadores de derechos humanos del planeta.",
        defensa: "Ese tipo de acusaciones gratuitas no se sostienen.", d: -6 }
    ]
  },
  {
    tema: "La votación de hoy",
    opciones: [
      { t: "Hoy el mundo no vota contra Cuba: vota contra el bloqueo. Cada voto a favor de esta resolución es un voto por el derecho internacional y contra las medidas coercitivas unilaterales. ¿Qué le dirá a los 187 países que ya se pronunciaron?",
        defensa: "Respetamos la opinión de la Asamblea, pero mantendremos el bloqueo mientras Cuba no cambie.", d: 12 },
      { t: "Esta votación demuestra que el bloqueo es una política fracasada que aísla a quien la aplica, no a quien la recibe.",
        defensa: "No es un fracaso: es una herramienta que seguiremos usando.", d: 9 },
      { t: "El mundo está cansado de sus sanciones unilaterales.",
        defensa: "Nuestras sanciones son legales y están dirigidas a un gobierno, no a un pueblo.", d: 5 },
      { t: "Su gobierno pasará a la historia como el último defensor del bloqueo.",
        defensa: "La historia nos juzgará, pero no nos doblegaremos.", d: 2 },
      { t: "Váyanse a casa, ya perdieron.",
        defensa: "La arrogancia no es un argumento, señor canciller.", d: -10 }
    ]
  },
  {
    tema: "La inclusión de Cuba en la lista de países patrocinadores del terrorismo",
    opciones: [
      { t: "Cuba fue incluida en la lista en 2021 por razones políticas, no técnicas. Colombia, país afectado por el conflicto, ha pedido su exclusión. Esa designación impide el acceso a servicios financieros y agrava el bloqueo.",
        defensa: "La designación se basa en informes de inteligencia y en la presencia de miembros del ELN en La Habana.", d: 12 },
      { t: "Cuba ha sido víctima de terrorismo: 3.478 muertos por atentados financiados desde el exterior. ¿Cómo puede ser patrocinadora?",
        defensa: "La lista evalúa cooperación antiterrorista, no victimización.", d: 9 },
      { t: "La inclusión es unilateral y contradice la posición de la mayoría de la comunidad internacional.",
        defensa: "Es una decisión soberana de Estados Unidos.", d: 6 },
      { t: "Esa lista es política.",
        defensa: "Todas las listas tienen un componente político.", d: 2 },
      { t: "Solo ustedes creen en esa lista.",
        defensa: "Otros países también tienen listas.", d: -5 }
    ]
  },
  {
    tema: "La base naval de Guantánamo",
    opciones: [
      { t: "Guantánamo es una prisión sin juicios ni garantías, en territorio cubano ocupado contra la voluntad de Cuba. ¿Con qué autoridad moral sancionan a otros por derechos humanos?",
        defensa: "Guantánamo es un asunto de seguridad nacional y sus detenidos son combatientes enemigos.", d: 12 },
      { t: "Cuba exige la devolución de Guantánamo desde 1959. Estados Unidos se niega a negociar.",
        defensa: "El arrendamiento es un tratado de 1903 vigente.", d: 9 },
      { t: "En Guantánamo se han documentado torturas y detenciones arbitrarias.",
        defensa: "Esas denuncias han sido investigadas y no se han probado.", d: 6 },
      { t: "Primero cierren Guantánamo y después hablamos.",
        defensa: "Guantánamo no tiene relación con el bloqueo.", d: 2 },
      { t: "Son unos hipócritas.",
        defensa: "Con insultos no se avanza.", d: -6 }
    ]
  },
  {
    tema: "El bloqueo durante la pandemia de COVID-19",
    opciones: [
      { t: "Durante la pandemia, Estados Unidos impidió que Cuba comprara ventiladores y mascarillas. Eso costó vidas. ¿Cómo lo justifica?",
        defensa: "Las licencias humanitarias existían y Cuba rechazó ayuda.", d: 12 },
      { t: "Cuba desarrolló sus propias vacunas y las compartió con el mundo, mientras el bloqueo impedía comprar insumos.",
        defensa: "Reconocemos el esfuerzo cubano, pero el bloqueo no es la causa.", d: 9 },
      { t: "Las sanciones no deberían aplicarse en una emergencia sanitaria global.",
        defensa: "Las sanciones tienen excepciones humanitarias.", d: 6 },
      { t: "La pandemia mostró la crueldad del bloqueo.",
        defensa: "La pandemia mostró la necesidad de cooperación.", d: 2 },
      { t: "Fueron cómplices de muertes.",
        defensa: "Esa acusación es grave e infundada.", d: -7 }
    ]
  },
  {
    tema: "El uso de la OEA contra Cuba",
    opciones: [
      { t: "La OEA, bajo influencia de Washington, ha sido utilizada para aislar a Cuba. Varios países han denunciado su funcionamiento.",
        defensa: "La OEA es un foro multilateral donde los países deciden libremente.", d: 12 },
      { t: "Cuba fue expulsada de la OEA en 1962 por presión de Estados Unidos y nunca debió serlo.",
        defensa: "La expulsión fue una decisión de la mayoría de los miembros.", d: 8 },
      { t: "La OEA ha sido parcial en casos como Venezuela y Bolivia.",
        defensa: "La OEA actúa según sus estatutos.", d: 5 },
      { t: "La OEA no es el mundo.",
        defensa: "Es el foro regional donde Cuba debería estar.", d: 2 },
      { t: "La OEA es un club de Washington.",
        defensa: "Esa simplificación no ayuda.", d: -5 }
    ]
  },
  {
    tema: "El internacionalismo médico cubano",
    opciones: [
      { t: "Más de 400.000 médicos cubanos han servido en 160 países. Esa es la imagen real de Cuba, no la que ustedes pintan.",
        defensa: "Reconocemos la labor médica, pero cuestionamos el programa de misiones.", d: 12 },
      { t: "Cuba ha enviado brigadas médicas a Italia, África y América Latina, incluso bajo bloqueo.",
        defensa: "Es una labor loable, pero no cambia la naturaleza del régimen.", d: 9 },
      { t: "Los médicos cubanos son voluntarios y han salvado millones de vidas.",
        defensa: "Algunos han denunciado condiciones de trabajo.", d: 6 },
      { t: "Cuba es solidaridad.",
        defensa: "La solidaridad no exime de responsabilidades.", d: 3 },
      { t: "El mundo debería estar agradecido.",
        defensa: "El mundo valora la ayuda, pero también la libertad.", d: -2 }
    ]
  },
  {
    tema: "La escasez de alimentos y medicinas",
    opciones: [
      { t: "El bloqueo es la causa principal de la escasez de alimentos y medicinas en Cuba. Las licencias son inoperantes por el miedo a las multas.",
        defensa: "Las compras de alimentos y medicinas están permitidas.", d: 12 },
      { t: "Cuba tiene que comprar medicinas a terceros países con sobreprecio por el bloqueo.",
        defensa: "Puede comprar en cualquier mercado.", d: 8 },
      { t: "El bloqueo impide el acceso a tecnología médica de empresas estadounidenses o con componentes estadounidenses.",
        defensa: "Existen licencias para eso.", d: 5 },
      { t: "El bloqueo mata.",
        defensa: "Esa es una exageración.", d: 2 },
      { t: "Ustedes son responsables.",
        defensa: "No aceptamos esa acusación.", d: -4 }
    ]
  },
  {
    tema: "Las remesas y la separación de familias",
    opciones: [
      { t: "El bloqueo limita las remesas y separa a las familias cubanas. ¿Cómo se justifica?",
        defensa: "Las remesas están permitidas con límites y excepciones.", d: 12 },
      { t: "Cuba denuncia que las restricciones a las remesas y a los viajes afectan a las familias.",
        defensa: "Las restricciones buscan evitar el financiamiento del gobierno.", d: 9 },
      { t: "La separación de familias es una consecuencia humana del bloqueo.",
        defensa: "La política de remesas ha sido revisada.", d: 6 },
      { t: "Las familias cubanas sufren por sus decisiones.",
        defensa: "Nuestras decisiones buscan un cambio positivo.", d: 3 },
      { t: "Eso es crueldad.",
        defensa: "No es crueldad, es política.", d: -3 }
    ]
  },
  {
    tema: "El bloqueo y el desarrollo sostenible",
    opciones: [
      { t: "El bloqueo impide que Cuba acceda a financiamiento internacional, tecnología limpia y mercados. Es un obstáculo al desarrollo sostenible y a los ODS.",
        defensa: "Cuba puede acceder a financiamiento multilateral si cumple requisitos.", d: 12 },
      { t: "Cuba no puede importar equipos para energías renovables por el bloqueo.",
        defensa: "Existen licencias para tecnología verde.", d: 8 },
      { t: "El bloqueo viola el derecho al desarrollo.",
        defensa: "El derecho al desarrollo no justifica un régimen.", d: 5 },
      { t: "El bloqueo frena el progreso.",
        defensa: "El progreso depende de políticas internas.", d: 2 },
      { t: "Es un crimen.",
        defensa: "Ese lenguaje no ayuda.", d: -4 }
    ]
  },
  {
    tema: "El historial de derechos humanos de Estados Unidos",
    opciones: [
      { t: "Estados Unidos tiene la mayor población carcelaria del mundo, mantiene la pena de muerte y ha cometido abusos en Irak y Afganistán. ¿Con qué autoridad moral sancionan a Cuba?",
        defensa: "No somos perfectos, pero rendimos cuentas.", d: 12 },
      { t: "Estados Unidos no ha ratificado varios tratados de derechos humanos, incluida la Convención de los Derechos del Niño.",
        defensa: "Tenemos nuestros propios mecanismos de protección.", d: 9 },
      { t: "La policía estadounidense mata a más personas que muchos gobiernos.",
        defensa: "Son casos individuales.", d: 6 },
      { t: "Primero limpien su casa.",
        defensa: "Nuestro sistema es democrático.", d: 2 },
      { t: "Son el imperio del mal.",
        defensa: "Esa retórica es propia de otros tiempos.", d: -6 }
    ]
  },
  {
    tema: "El futuro de las relaciones Cuba-Estados Unidos",
    opciones: [
      { t: "El bloqueo es una política fracasada que aísla a Estados Unidos y no a Cuba. Es hora de un diálogo respetuoso y sin condiciones.",
        defensa: "Estamos abiertos al diálogo si Cuba avanza en derechos humanos.", d: 12 },
      { t: "La mayoría de los estadounidenses apoya el fin del bloqueo. ¿Por qué no escuchan a su pueblo?",
        defensa: "El Congreso decide la política hacia Cuba.", d: 9 },
      { t: "Cuba ha propuesto diálogo en múltiples ocasiones y Estados Unidos lo ha rechazado.",
        defensa: "Hemos tenido contactos.", d: 6 },
      { t: "El futuro está en la normalización.",
        defensa: "El futuro depende de cambios internos.", d: 3 },
      { t: "El bloqueo caerá solo.",
        defensa: "Mientras tanto, seguiremos firmes.", d: -2 }
    ]
  }
];

/* =========================================================
   ESTADO
   ========================================================= */
let fase = 1, ronda = 0, puntos = 50, bloqueado = false;
let rondasFase1 = [], rondasFase2 = [];
const $ = id => document.getElementById(id);

/* =========================================================
   CARA DEL SECRETARIO DE ESTADO
   ========================================================= */
function nivelDe(p){
  if (p < 35) return 0;   // él va ganando: sonrisa burlona
  if (p < 50) return 1;   // satisfecho
  if (p < 65) return 2;   // neutral
  if (p < 80) return 3;   // preocupado
  return 4;               // furioso / perdiendo
}

function setFace(nivel){
  const cara=$('cara'), boca=$('boca'), cejaL=$('cejaL'), cejaR=$('cejaR'),
        sudor=$('sudor'), sudor2=$('sudor2'), ojoL=$('ojoL'), ojoR=$('ojoR'),
        pupL=$('pupL'), pupR=$('pupR'), rubor=$('rubor'), rubor2=$('rubor2');

  ojoL.setAttribute('ry','12'); ojoR.setAttribute('ry','12');
  pupL.setAttribute('r','7');   pupR.setAttribute('r','7');
  sudor.setAttribute('opacity','0'); sudor2.setAttribute('opacity','0');
  rubor.setAttribute('opacity','0'); rubor2.setAttribute('opacity','0');
  cara.setAttribute('fill','#f3c9a6');

  switch(nivel){
    case 0:
      cejaL.setAttribute('d','M96 104 L140 98');
      cejaR.setAttribute('d','M204 104 L160 98');
      boca.setAttribute('d','M112 184 Q150 216 188 184');
      boca.setAttribute('stroke-width','6');
      ojoL.setAttribute('ry','9'); ojoR.setAttribute('ry','9');
      break;
    case 1:
      cejaL.setAttribute('d','M96 110 L140 104');
      cejaR.setAttribute('d','M204 110 L160 104');
      boca.setAttribute('d','M116 190 Q150 206 184 190');
      boca.setAttribute('stroke-width','6');
      break;
    case 2:
      cejaL.setAttribute('d','M96 110 L140 108');
      cejaR.setAttribute('d','M204 110 L160 108');
      boca.setAttribute('d','M118 192 L182 192');
      boca.setAttribute('stroke-width','6');
      break;
    case 3:
      cejaL.setAttribute('d','M96 100 L140 116');
      cejaR.setAttribute('d','M204 100 L160 116');
      boca.setAttribute('d','M114 198 Q150 176 186 198');
      boca.setAttribute('stroke-width','7');
      ojoL.setAttribute('ry','14'); ojoR.setAttribute('ry','14');
      sudor.setAttribute('opacity','1');
      break;
    case 4:
      cara.setAttribute('fill','#ee9d7c');
      cejaL.setAttribute('d','M94 96 L140 122');
      cejaR.setAttribute('d','M206 96 L160 122');
      boca.setAttribute('d','M108 202 Q150 168 192 202');
      boca.setAttribute('stroke-width','8');
      ojoL.setAttribute('ry','15'); ojoR.setAttribute('ry','15');
      pupL.setAttribute('r','5');   pupR.setAttribute('r','5');
      sudor.setAttribute('opacity','1'); sudor2.setAttribute('opacity','1');
      rubor.setAttribute('opacity','0.7'); rubor2.setAttribute('opacity','0.7');
      break;
  }
}

/* =========================================================
   PREPARAR RONDAS ALEATORIAS
   ========================================================= */
function prepararRondas(){
  rondasFase1 = elegirAleatorios(FASE1, 5).map(r => ({
    ataque: r.ataque,
    opciones: shuffle(r.opciones)
  }));
  rondasFase2 = elegirAleatorios(FASE2, 5).map(r => ({
    tema: r.tema,
    opciones: shuffle(r.opciones)
  }));
}

/* =========================================================
   FLUJO DEL JUEGO
   ========================================================= */
function iniciarJuego(){
  fase = 1; ronda = 0; puntos = 50; bloqueado = false;
  prepararRondas();

  $('inicio').classList.add('oculto');
  $('final').classList.add('oculto');
  $('juego').classList.remove('oculto');

  $('caraContenedor').appendChild($('canciller'));

  actualizarMedidor();
  setFace(nivelDe(puntos));
  mostrarRonda();
}

function actualizarMedidor(){
  $('puntosTxt').textContent = puntos;
  const f = $('barraFill');
  f.style.width = puntos + '%';
  f.style.background = puntos >= 65
      ? 'linear-gradient(90deg,#4ad991,#7fd0ff)'
      : puntos >= 40
        ? 'linear-gradient(90deg,#f2b544,#4ad991)'
        : 'linear-gradient(90deg,#ff6b6b,#f2b544)';
}

function mostrarRonda(){
  bloqueado = false;
  $('narracion').textContent = '';
  $('btnContinuar').classList.add('oculto');
  $('opciones').innerHTML = '';

  const esFase1 = (fase === 1);
  const datos = esFase1 ? rondasFase1[ronda] : rondasFase2[ronda];

  $('etiquetaFase').textContent =
    'Ronda ' + (ronda + 1) + ' de 5 · ' +
    (esFase1 ? 'Él ataca — tú respondes' : 'Tú atacas — él se defiende');

  if (esFase1){
    $('temaRonda').textContent = 'El Secretario de Estado toma la palabra:';
    $('burbuja').textContent = '“' + datos.ataque + '”';
  } else {
    $('temaRonda').textContent = 'Tema: ' + datos.tema + '. Elige tu ataque.';
    $('burbuja').textContent = '“Adelante, señor canciller. Exponga su argumento. El mundo nos escucha.”';
  }

  const cont = $('opciones');
  datos.opciones.forEach((op, i) => {
    const b = document.createElement('button');
    b.className = 'opcion';
    b.innerHTML = '<span class="num">' + (i + 1) + '</span><span></span>';
    b.querySelector('span:last-child').textContent = op.t;
    b.onclick = () => elegir(op);
    cont.appendChild(b);
  });
}

function elegir(op){
  if (bloqueado) return;
  bloqueado = true;

  document.querySelectorAll('.opcion').forEach(b => b.disabled = true);

  puntos = Math.max(0, Math.min(100, puntos + op.d));

  if (fase === 1){
    $('burbuja').textContent = '“' + reaccion(op.d) + '”';
  } else {
    $('burbuja').textContent = '“' + op.defensa + '”';
  }

  $('narracion').textContent = narrativa(op.d);

  mostrarDelta(op.d);
  actualizarMedidor();
  setFace(nivelDe(puntos));

  $('btnContinuar').classList.remove('oculto');
}

function mostrarDelta(d){
  const el = $('delta');
  el.textContent = (d > 0 ? '+' : '') + d;
  el.className = 'delta ' + (d > 0 ? 'pos' : (d < 0 ? 'neg' : 'neu'));
  void el.offsetWidth;
  el.classList.add('animar');
}

function reaccion(d){
  if (d >= 10) return '¡Eso no responde a lo que pregunté! Está sacando las cosas de contexto...';
  if (d >= 5)  return 'Concedo ese punto... pero no cambia el fondo del asunto.';
  if (d >= 1)  return 'Interesante. Aunque insuficiente, por supuesto.';
  if (d >= -4) return 'Exactamente. Gracias por confirmar mi posición.';
  return 'Veo que no tienen argumentos. El mundo lo está notando.';
}

function narrativa(d){
  if (d >= 10) return 'La sala reacciona con murmullos de aprobación. Varias delegaciones toman nota a favor de Cuba.';
  if (d >= 5)  return 'Algunas delegaciones asienten: el argumento gana terreno.';
  if (d >= 1)  return 'El efecto es moderado; la sala permanece dividida.';
  if (d >= -4) return 'La intervención no convence a nadie y el apoyo se estanca.';
  return 'Varias delegaciones evitan mirar a la bancada cubana. El apoyo se resquebraja.';
}

function continuar(){
  ronda++;
  if (fase === 1 && ronda >= 5){
    fase = 2; ronda = 0;
    $('burbuja').textContent = '“Muy bien, canciller. Ahora le toca a usted atacar. Veamos de qué está hecho.”';
    $('narracion').textContent = 'Cambio de turno: ahora tus argumentos deben hacer tambalear su defensa.';
    setTimeout(mostrarRonda, 900);
    $('btnContinuar').classList.add('oculto');
    return;
  }
  if (fase === 2 && ronda >= 5){ terminar(); return; }
  mostrarRonda();
}

/* =========================================================
   RESULTADO FINAL
   ========================================================= */
function terminar(){
  const favor  = Math.min(189, Math.round(70 + puntos * 1.18));
  const contra = Math.max(2, Math.round(28 - puntos * 0.26));
  const abst   = Math.max(0, 193 - favor - contra);

  $('juego').classList.add('oculto');
  $('final').classList.remove('oculto');

  $('caraFinal').appendChild($('canciller'));
  setFace(nivelDe(puntos));

  animarNumero('vFavor', favor);
  animarNumero('vContra', contra);
  animarNumero('vAbst', abst);

  let titulo, mensaje;
  if (favor >= 170){
    titulo = '¡Victoria histórica!';
    mensaje = 'La resolución se aprueba con una mayoría abrumadora. El Secretario de Estado queda completamente aislado: su propio bloque de aliados se reduce a dos votos. Cuba gana la batalla diplomática del año.';
  } else if (favor >= 140){
    titulo = 'Amplia mayoría';
    mensaje = 'El mundo vuelve a pronunciarse contra el bloqueo con una diferencia contundente. Aunque Washington insiste en su política, el aislamiento queda retratado ante las cámaras.';
  } else if (favor >= 110){
    titulo = 'Mayoría suficiente';
    mensaje = 'La resolución pasa, pero el margen no es todo lo amplio que Cuba esperaba. Algunas delegaciones prefirieron la abstención y el Secretario de Estado respira algo más tranquilo.';
  } else if (favor >= 85){
    titulo = 'Mayoría simple y nada más';
    mensaje = 'La resolución se aprueba por un margen ajustado. El Secretario de Estado sonríe de lado: logró dividir a la sala y restarle fuerza al pronunciamiento contra el bloqueo.';
  } else {
    titulo = 'La resolución no despega';
    mensaje = 'El apoyo internacional se fragmenta y las abstenciones se multiplican. El Secretario de Estado abandona la sala con gesto victorioso: el bloqueo resiste un año más.';
  }

  $('tituloFinal').textContent = titulo;
  $('mensajeFinal').textContent = mensaje;
}

function animarNumero(id, valor){
  const el = $(id);
  let actual = 0;
  const paso = Math.max(1, Math.round(valor / 28));
  const t = setInterval(() => {
    actual += paso;
    if (actual >= valor){ actual = valor; clearInterval(t); }
    el.textContent = actual;
  }, 28);
}

/* arranque */
setFace(2);
</script>
</body>
</html>
