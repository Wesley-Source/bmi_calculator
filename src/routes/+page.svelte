<script>
  let weight_kg = $state(0.0);
  let height_cm = $state(0.0);

  let bmi = $derived(height_cm > 0 ? weight_kg / ((height_cm / 100) ** 2) : 0);
</script>

<header
  class="w-full bg-[#F8E8EE] py-3 sm:py-4 md:py-5 lg:py-6 shadow-md block"
>
  <h1
    class="text-3xl sm:text-3xl md:text-4xl lg:text-5xl text-center text-[#F2BED1] text-shadow-lg"
  >
    Calculadora de IMC
  </h1>
</header>

<main class="flex flex-col items-center justify-center space min-h-[70vh] w-full drop-shadow-lg">
  <div
    class="bg-[#F8E8EE] rounded-2xl shadow-lg p-8 w-full max-w-md flex flex-col items-center"
  >
    <form class="w-full flex flex-col gap-2 ">
      <label class="text-2xl sm:text-2xl md:text-3xl lg:text-3xl flex flex-col">
        Peso (kg):
        <input
          type="text"
          bind:value={weight_kg}
          name="weight"
          id="weight"
          placeholder="Ex: 65"
          required
        />
      </label>
      <label class="text-2xl sm:text-2xl md:text-3xl lg:text-3xl flex flex-col">
        Altura (cm):
        <input
          type="text"
          bind:value={height_cm}
          name="height"
          id="height"
          placeholder="Ex: 170"
          required
        />
      </label>
    </form>
    <div class="p-auto w-full h-full">

      <h1 class="text-[whitesmoke] text-center ">{bmi ? bmi.toFixed(1) : ""}</h1>
    </div>
  </div>
</main>

<style>
</style>
