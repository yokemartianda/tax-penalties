<script lang="ts">
    import CalculateButton from "./lib/CalculateButton.svelte";
    let pajak: number;
    let bulan: number;
</script>

<main class="container">
    <div class="flex h-screen">
        <div class="m-auto text-center">
            <div class="mb-20">
                <h1 class="text-3xl leading-tight">
                    Hitung Denda Pajak Kendaraan
                </h1>
                <span>
                    Hitung biaya denda pajak kendaraan anda dengan menggunakan
                    aplikasi ini
                </span>
            </div>
            <div class="mt-4">
                <span class="mr-1">Jumlah PKB Rp </span>
                <input
                    type="text"
                    name="pajak"
                    bind:value={pajak}
                    id="pajak"
                    class="form-control
                    px-1
                    py-0.5
                    w-40
                    text-base
                    font-normal
                    text-gray-700
                    bg-white bg-clip-padding
                    border border-solid border-gray-300
                    rounded
                    transition
                    ease-in-out
                    m-0
                    focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none"
                    required
                />
                <span class="ml-1" />
            </div>
            <div class="mt-4">
                <span class="mr-1">Lama keterlambatan :</span>
                <input
                    type="text"
                    name="bulan"
                    bind:value={bulan}
                    id="bulan"
                    class="form-control
                    px-1
                    py-0.5
                    w-40
                    text-base
                    font-normal
                    text-gray-700
                    bg-white bg-clip-padding
                    border border-solid border-gray-300
                    rounded
                    transition
                    ease-in-out
                    m-0
                    focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none"
                    required
                />
                <span class="ml-1">Bulan</span>
            </div>
            <div class="mt-2">
                <CalculateButton {bulan} {pajak} />
            </div>
        </div>
    </div>
</main>
