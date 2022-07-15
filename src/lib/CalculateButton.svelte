<script lang="ts">
    export let bulan: number;
    export let pajak: number;
    let totalPenalties: number = 0;
    let totalFormatted: string;
    let isClicked = false;
    let err = false;
    function calculatePenalties() {
        if (!isNaN(pajak) && !isNaN(bulan)) {
            totalPenalties = Math.round(pajak * 0.25 * (bulan / 12) + 35000);
            if (bulan > 12) {
                bulan = 12;
                totalPenalties = Math.round(
                    2 * pajak * 0.25 * (bulan / 12) + 35000
                );
            }
            totalFormatted = totalPenalties
                .toString()
                .replace(/\B(?<!\.\d*)(?=(\d{3})+(?!\d))/g, ".");
            isClicked = true;
            err = false;
        } else {
            err = true;
            isClicked = false;
        }
    }
</script>

<main>
    <button
        type="submit"
        class="py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-lime-600 hover:bg-lime-700"
        on:click={() => calculatePenalties()}>Hitung!</button
    >
    {#if err}
        <h3 class="mt-2 text-1l text-red-600 dark:text-red-500 font-medium">
            Hanya dapat menerima input berupa angka!
        </h3>
    {/if}
    {#if isClicked}
        <h3 class="mt-2 text-2l">Jumlah denda adalah Rp {totalFormatted}</h3>
    {/if}
</main>
