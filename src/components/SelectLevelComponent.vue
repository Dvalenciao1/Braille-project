<template>
  <q-card
    :flat="$q.screen.lt.md"
    :style="{
      'background-color': $q.screen.lt.md ? '#ffe0b2' : '#f69e53',
      width: $q.screen.lt.md ? 100 + '%' : 35 + '%',
      height: 500 + 'px',
    }"
    class="my-card column"
  >
    <q-card-section class="col-2 q-pt-lg q-pl-lg">
      <span class="text-h6 text-weight-semibold">Seleccione un nivel:</span>
    </q-card-section>
    <q-card-actions vertical class="col-10 items-evenly">
      <q-btn
        class="q-ma-lg col-2"
        style="
          background-color: #5373c6;
          color: #fff;
          border-radius: 10px;
          font-size: 22px;
        "
        label="Principiante"
        no-caps
        to="/init/play/1"
      />
      <q-btn
        class="q-ma-lg col-2"
        style="
          background-color: #5373c6;
          color: #fff;
          border-radius: 10px;
          font-size: 22px;
        "
        label="Intermedio"
        no-caps
        to="/init/play/2"
      />
      <q-btn
        class="q-ma-lg col-2"
        style="
          background-color: #5373c6;
          color: #fff;
          border-radius: 10px;
          font-size: 22px;
        "
        label="Avanzado"
        no-caps
        to="/init/play/3"
      />
    </q-card-actions>
  </q-card>
</template>
