<template>
    <footer class="bg-[#fcfcfc]">
        <div class="mx-auto max-w-8xl">
            <div class="grid grid-cols-1 lg:grid-cols-4 md:grid-cols-2 gap-5 lg:pt-8 py-3 px-3">
                <div>
                    <nuxt-link :to="'/'" class="text-3xl lg:text-4xl capitalize font-mono">emmila</nuxt-link>
                    <p class="text-[#b0b0b8] pt-5 text-sm">Geniş ürün yelpazemizi keşfedin ve güvenle online alışverişin keyfini çıkarın.</p>
                    </div>
                    <div>
                        <h4 class="text-lg font-semibold">EMMILA</h4>
                        <ul class="text-[#9da5af] space-y-3 pt-3 text-sm">
                            <li>Hikayemiz</li>
                            <li>İletişim</li>
                            <li>Sıkça Sorulan Sorular</li>

                        </ul>
                    </div>
                    <div>
                        <h4 class="text-lg font-semibold">HİZMETLER</h4>
                        <ul class="text-[#9da5af] space-y-3 pt-3 text-sm">
                            <li>Gizlilik Politikası</li>
                            <li>İade Politikası</li>
                            <li>Teslimat Bilgileri</li>
                            <li>Mesafeli Satış Sözleşmesi</li>
                            <li>Çerez Politikası</li>
                        </ul>
                    </div>
                    <div>
                        <h4 class="text-lg font-semibold">İLETİŞİM</h4>
                        <ul class="text-[#9da5af] space-y-3 pt-3 text-sm">
                            <li>info@emmila.com</li>
                        </ul>
                    </div>
                </div>
                <hr class="border border-solid border-gray-100 lg:mt-8" />
                <div class="lg:flex justify-between items-center pt-5 pb-8">
                    <div class="text-[#9da5af] lg:ml-0 ml-3">
                        <h1>
                            © 2023 <span class="">Emmila.</span> Tüm hakları saklıdır.
                        </h1>
                    </div>
                    <div>
                        <ul class="flex gap-2 lg:ml-0 ml-3 lg:mt-0 mt-3">
                            <li>
                                <div
                                class="flex lg:col-span-2 h-10 w-10 rounded-md bg-[#f8f8f8] items-center justify-center"
                                >
                                <Icon name="gg:facebook" size="20" />
                            </div>
                        </li>
                        <li>
                            <div
                            class="flex lg:col-span-2 h-10 w-10 rounded-md bg-[#f8f8f8] items-center justify-center"
                            >
                            <Icon name="jam:linkedin" size="20" />
                        </div>
                    </li>
                    <li>
                        <div
                        class="flex lg:col-span-2 h-10 w-10 rounded-md bg-[#f8f8f8] items-center justify-center"
                        >
                        <Icon name="mdi:twitter" size="20" />
                    </div>
                </li>
                <li>
                    <div
                    class="flex lg:col-span-2 h-10 w-10 rounded-md bg-[#f8f8f8] items-center justify-center"
                    >
                    <Icon name="mdi:youtube" size="20" />
                </div>
            </li>
        </ul>
    </div>
</div>
</div>
</footer>
</template>
