<template>
  <div class="bg-[#FBFAFF] overflow-hidden pb-0">
    <div class="bg-[#25101F] text-white grid grid-rows-1 grid-flow-col w-screen">
      <div class="pt-5 pb-5 grid grid rows-1 grid-flow-col gap-5  justify-center">
        <div class="flex flex-1 place-items-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" color="#DDA92B" fill="currentColor"
            class="bi bi-telephone-fill" viewBox="0 0 16 16">
            <path fill-rule="evenodd"
              d="M1.885.511a1.745 1.745 0 0 1 2.61.163L6.29 2.98c.329.423.445.974.315 1.494l-.547 2.19a.68.68 0 0 0 .178.643l2.457 2.457a.68.68 0 0 0 .644.178l2.189-.547a1.75 1.75 0 0 1 1.494.315l2.306 1.794c.829.645.905 1.87.163 2.611l-1.034 1.034c-.74.74-1.846 1.065-2.877.702a18.6 18.6 0 0 1-7.01-4.42 18.6 18.6 0 0 1-4.42-7.009c-.362-1.03-.037-2.137.703-2.877z" />
          </svg>
          <p class="ml-2">Être rappelé</p>
        </div>
        <div class="flex flex-1 place-items-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" color="#DDA92B" fill="currentColor"
            class="bi bi-calendar-check-fill" viewBox="0 0 16 16">
            <path
              d="M4 .5a.5.5 0 0 0-1 0V1H2a2 2 0 0 0-2 2v1h16V3a2 2 0 0 0-2-2h-1V.5a.5.5 0 0 0-1 0V1H4zM16 14V5H0v9a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2m-5.146-5.146-3 3a.5.5 0 0 1-.708 0l-1.5-1.5a.5.5 0 0 1 .708-.708L7.5 10.793l2.646-2.647a.5.5 0 0 1 .708.708" />
          </svg>
          <p class="ml-2">Prendre RDV</p>
        </div>

      </div>
      <div class=" grid grid rows-1 grid-flow-col gap-5 flex justify-center">
        <div class="flex flex-1 place-items-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" color="#DDA92B"
            class="bi bi-send-fill" viewBox="0 0 16 16">
            <path
              d="M15.964.686a.5.5 0 0 0-.65-.65L.767 5.855H.766l-.452.18a.5.5 0 0 0-.082.887l.41.26.001.002 4.995 3.178 3.178 4.995.002.002.26.41a.5.5 0 0 0 .886-.083zm-1.833 1.89L6.637 10.07l-.215-.338a.5.5 0 0 0-.154-.154l-.338-.215 7.494-7.494 1.178-.471z" />
          </svg>
          <p class="ml-2">Formulaire de contact</p>
        </div>
        <div class="flex flex-1 place-items-center">
          <Icon icon="ion:ios-chatbubbles" class="text-[19px] text-[#DDA92B]" />
          <p class="ml-2">Chat en ligne</p>
        </div>

      </div>
    </div>
    <div class="grid grid-rows-1 grid-flow-col gap-5 pt-10 pb-10">
      <div class="pt-5 flex flex-1 place-items-center justify-end font-bold text-[#493D47]">
        <img src="./images/Forma-1-copy.png" />
        <p class="ml-4"> 01 42 89 53 18 <br>
          contact@antheor-paris.fr</p>
      </div>
      <div class="pt-5 flex flex-1 place-items-center justify-center">
        <img src="./images/logo-header.png">
      </div>
      <div class="flex flex-1 place-items-center">
        <img src="./images/L1-copy.png" />
        <p class="font-bold ml-2 text-[#493D47]">8,RUE CORVETTO <br>75008 PARIS</p>
      </div>
    </div>
    <Disclosure as="nav" class="border-t-2 " v-slot="{ open }">
      <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
        <div class="relative flex h-16 items-center justify-between">
          <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
            <!-- Mobile menu button-->
            <DisclosureButton
              class="relative inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white">
              <span class="absolute -inset-0.5" />
              <span class="sr-only">Open main menu</span>
              <Bars3Icon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
              <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
            </DisclosureButton>
          </div>
          <div class="flex flex-1 items-center justify-center sm:items-stretch sm:justify-start">

            <div class="hidden sm:ml-6 sm:block">
              <div class="flex space-x-4 font-semi-bold">
                <a v-for="item in navigation" :key="item.name" :href="item.href"
                  :class="[item.current ? 'text-[#D3A635]' : 'text-black']"
                  :aria-current="item.current ? 'page' : undefined">{{ item.name }}</a>
              </div>
            </div>
          </div>
        </div>
      </div>

      <DisclosurePanel class="sm:hidden">
        <div class="space-y-1 px-2 pb-3 pt-2">
          <DisclosureButton v-for="item in navigation" :key="item.name" as="a" :href="item.href"
            :class="[item.current ? 'bg-gray-900 text-white' : 'text-gray-300 hover:bg-gray-700 hover:text-white', 'block rounded-md px-3 py-2 text-base font-medium']"
            :aria-current="item.current ? 'page' : undefined">{{ item.name }}</DisclosureButton>
        </div>
      </DisclosurePanel>
    </Disclosure>
    <Carousel class="z-0">
      <Slide v-for="slide in 10" :key="slide">
        <div class="carousel__item">
          <img src="./images/Group-11.jpg" />
        </div>
      </Slide>

      <template #addons>
        <Navigation />
        <Pagination />
      </template>
    </Carousel>
    <div class="absolute -mt-[18%] z-1 text-white ml-[10%] w-[80%]">
      <div class="grid grid-rows-1 grid-flow-col items-center">
        <hr class="w-[10%] border-[#A88730] border-2" />
        <p class="-ml-[75%] uppercase font-light">
          anthéor paris
        </p>
      </div>
      <div class="text-5xl font-light">
        <p>Rachat d'or a Paris (paiment comptant par chéque)</p>
        <p class="text-3xl mt-2">Nous achetons votre or sous toutes ses formes : <br>
          <span class="text-[#BC8D19] font-bold text-2xl mt-2">(Débris or, or cassé, bijoux en or, vieil or, lingots or,
            piéces en
            or...)</span>
        </p>
      </div>
    </div>
    <div class="grid grid-cols-2 text-[#2F1C2A] ml-[15%] mt-10 ">
      <div class="bg-white p-5 w-[87%] h-[60%] drop-shadow-xl">
        <p class="text-[#DEBD6C]">ANTHÉOR PARIS</p>
        <p class="text-3xl font-semibold ml-2">Nous somme spécialisés dans le rachat d'Or, <br> d'Argent d'Atiquités,
          depuis
          plus de 20 ans .
        </p>
        <div class="grid grid-rows-1 grid-flow-col items-center mt-5">
          <Icon icon="tabler:check" class="text-[#DBB355] text-[20px]" />
          <p class="-ml-[14%] mt-5">
            Achat de métaux précieux : or (a 32$ le gramme de 18K et
            jusqu'a <br> 50£/g) -
            Argent - Platine
          </p>
        </div>
        <div class="grid grid-rows-1 grid-flow-col items-center mt-5">
          <Icon icon="tabler:check" class="text-[#DBB355] text-[20px]" />
          <p class="-ml-[37%] mt-0">
            Piéce or et argent - Lingots or et argent

          </p>
        </div>
        <div class="grid grid-rows-1 grid-flow-col items-center mt-5">
          <Icon icon="tabler:check" class="text-[#DBB355] text-[20px]" />
          <p class="-ml-[25%]">
            Argenterie ancienne (Odiot - Christofle - Puiforcat )
          </p>
        </div>
        <div class="grid grid-rows-1 grid-flow-col items-center mt-5">
          <Icon icon="tabler:check" class="text-[#DBB355] text-[20px]" />
          <p class="-ml-[7%]">
            Bijoux d'occasion, bijoux modernes, bijoux de marque
            (Van-Cleef,Cartier ... )
          </p>
        </div>
        <div class="grid grid-rows-1 grid-flow-col items-center mt-5">
          <Icon icon="tabler:check" class="text-[#DBB355] text-[20px]" />
          <p class="-ml-[15%]">
            Montres de marque (Rolex, Patek Philippe, Audemards Piguet...)
          </p>
        </div>
        <div class="grid grid-rows-1 grid-flow-col items-center mt-5">
          <Icon icon="tabler:check" class="text-[#DBB355] text-[20px]" />
          <p class="-ml-[12.5%]">
            Antiquités (Tableaux, Bronzed, Bibelots, Arts des années 30
            et 50... )
          </p>
        </div>

      </div>
      <div>
        <img src="./images/Rectangle-581.jpg" class="-ml-[10%]" alt="">
      </div>
      <div class="-mt-[35.2%]">
        <p class="absolute text-white font-regular text-center w-[36.9%] pt-[0.5%] text-2xl font-light">
          9.9/10 <br>
        <div class="grid grid-cols-6  w-[50%] ml-[33%] justify-items-center z-0 text-yellow-500 mt-2">
          <Icon icon="ic:outline-star-purple500" class="ml-[100%]" />
          <Icon icon="ic:outline-star-purple500" class="mr-[15%]" />
          <Icon icon="ic:outline-star-purple500" class="mr-[130%]" />
          <Icon icon="ic:outline-star-purple500" class="mr-[250%]" />
          <Icon icon="ic:outline-star-purple500" class="mr-[370%]" />
          <Icon icon="ic:outline-star-purple500" class="mr-[490%]" />

        </div>
        Excellent <br>
        Base sur 89 avis
        <img src="./images/Google-Reviews.png" class="ml-[38%] mt-6" />
        </p>

        <img src="./images/L00011.jpg" alt="">

      </div>
    </div>
    <div class="ml-[15%] mt-[5%] grid grid-cols-2 gap-2">
      <div class="">
        <div class="grid grid-rows-1 grid-flow-col items-center ">
          <hr class="w-[30%] border-[#E0C689] border-2" />
          <p class="uppercase font-semibold -ml-[40%] text-[#E0C689] text-2xl">
            anthéor paris
          </p>
        </div>
        <p class="text-[#362130] text-3xl font-bold mt-5">Comment se déroule le<br> rachat de votre or ?</p>
      </div>
      <div>
        <p class="text-3xl font-bold text-[#C49A31]">Expertise Gratuits</p>
        <p class="text-[#362130] font-bold text-xl mt-5">
          <Icon icon="mdi:home" class="absolute text-[#C69419] text-2xl mt-1" /><span class="ml-8">
            En boutique a Paris (Cadre sécurisé)</span>
        </p>
        <p class="text-[#362130] font-bold text-xl">
          <Icon icon="material-symbols:storefront-outline-rounded" class="absolute text-[#C69419] text-2xl mt-1" /> <span
            class="ml-8">Ou a
            votre
            Domicile
            (sur
            rendez-vous)
          </span>
        </p>
      </div>
    </div>
    <div class="mt-10">
      <p class="uppercase text-center text-[#E0C689]">
        anthéor paris
      </p>
      <h1 class="uppercase text-center font-semibold text-4xl text-[#362130] mt-1">prérequis</h1>
      <div class="grid grid-cols-3 gap-1 ml-[25%] mt-2">
        <hr class="w-[35%] border-[#D6CCD5] border-2 ml-[65.4%] mt-[1%]">
        <Icon icon="mdi:circle" class="text-[#E6AC1D] text-sm" />
        <hr class="w-[35%] border-[#D6CCD5] border-2 -ml-[97.5%] mt-[1%]">
      </div>
      <div class="grid grid-cols-2 gap-2 ml-[15%]">
        <div class="bg-white mt-5 w-[80%]">
          <div class="grid grid-rows-1 grid-flow-col items-center ">
            <Icon icon="mdi:card-account-details" class="bg-[#C69419] text-white text-9xl p-10" />
            <p class="text-2xl font-semibold -ml-[20%] text-[#362130]">N'oubliez pas de vous munir <br /> d'une piéce
              d'identité .</p>
          </div>

        </div>
        <div class="bg-white mt-5 w-[85%] -ml-10">
          <div class="grid grid-rows-1 grid-flow-col items-center ">
            <Icon icon="game-icons:injustice" class="bg-[#C69419] text-white text-9xl p-10" />
            <p class="text-2xl font-semibold -ml-[9%] text-[#362130]">La quantité minimale pour que nous <br />
              rachétions votre or est de 10 grammes.</p>
          </div>

        </div>

      </div>
    </div>
    <div class="mt-[9%] text-center">
      <p class="uppercase text-[#E0C689]">
        anthéor paris
      </p>
      <p class="text-[#362130] text-4xl font-semibold ml-1">Nous achetons, aux meilleurs prix, et comptant</p>
      <div class="grid grid-cols-3 gap-1 ml-[25%] mt-2">
        <hr class="w-[35%] border-[#D6CCD5] border-2 ml-[65.4%] mt-[1%]">
        <Icon icon="mdi:circle" class="text-[#E6AC1D] text-sm" />
        <hr class="w-[35%] border-[#D6CCD5] border-2 -ml-[97.5%] mt-[1%]">
      </div>
    </div>
    <div class="ml-[15%] mt-5 grid grid-flow-row-dense grid-rows-4 gap-3 grid-cols-4 w-[75%]">
      <div class="col-span-2"><img src="./images/Color-Fill-592.jpg" alt="" srcset="">
        <div class="text-white position absolute -mt-[5%] ml-5 font-bold ">
          <p class="text-xl">Or</p>
          <hr class="w-[3%] border-2 border-[#D1AD60]">
          <p class="font-light">Débris d'or - Or cassé - Or dentaire Médailles - Bracelets Colliers... a 32£ <br> le
            grammme de 18K et
            jusqua'a
            50£/g</p>
        </div>
      </div>
      <div class="col-span-2"><img src="./images/Rectangle-5781.jpg" alt="">
        <div class="text-white position absolute -mt-[5%] ml-5 font-bold ">
          <p class="text-xl uppercase">Piéce or & argent</p>
          <hr class="w-[3%] border-2 border-[#D1AD60]">
          <p class="font-light">Piéces francaise et étrangéres : Napoléon 20 Francs, 20 Dollars US, 50 <br>Pesos Mexicain,
            souvrain... </p>
        </div>
      </div>
      <div class="col-span-2"><img src="./images/Rectangle-5782.jpg" alt="">
        <div class="text-white position absolute -mt-[5%] ml-5 font-bold ">
          <p class="text-xl">BIJOUX & MONTRES</p>
          <hr class="w-[3%] border-2 border-[#D1AD60]">
          <p class="font-light">Montres de marque, pierres précieuses, bijoux d'occasion, bijoux mod-<br>ernes, bijoux de
            marque (Rolex, patek philippe...)</p>
        </div>
      </div>
      <div class="col-span-2"><img src="./images/Color-Fill-598.jpg" alt="" srcset="">
        <div class="text-white position absolute -mt-[5%] ml-5 font-bold ">
          <p class="text-xl">ARGENTERIE</p>
          <hr class="w-[3%] border-2 border-[#D1AD60]">
          <p class="font-light">Piéces de forme, couverts en métal argenté et argent massif (Odiot -<br>Christofle -
            Puiforcat... )
            grammme de 18K et
            jusqua'a
            50£/g</p>
        </div>
      </div>
      <div><img src="./images/diamond-classic.jpg" alt="" srcset="" class="">
        <div class="text-white position absolute -mt-[5%] ml-5 font-bold ">
          <p class="text-xl uppercase">Diamants</p>
          <hr class="w-[30%] border-2 border-[#D1AD60]">
        </div>
      </div>
      <div><img src="./images/Rectangle-5783.jpg" alt="" srcset="" class=" ml-[50%]">
        <div class="text-white position absolute -mt-[5%] ml-[10%] font-bold ">
          <p class="text-xl uppercase">Argent</p>
          <hr class="w-[30%] border-2 border-[#D1AD60]">
          <p class="font-light">Toutes piéces en argent massif</p>
        </div>
      </div>
      <div><img src="./images/Rectangle-5784.jpg" alt="" srcset="" class=" ml-[100%]">
        <div class="text-white position absolute -mt-[5%] ml-[19%] font-bold ">
          <p class="text-xl uppercase">Antiquités</p>
          <hr class="w-[30%] border-2 border-[#D1AD60]">
          <p class="font-light">Tableaux,scupltures, bronze, art asiatique, <br> art déco...</p>
        </div>
      </div>

    </div>
    <div class="-mt-[15%] text-center">
      <p class="uppercase text-[#E0C689]">
        anthéor paris
      </p>
      <p class="text-[#362130] text-4xl font-bold ml-1">Se rendre en Boutique</p>
      <div class="grid grid-cols-3 gap-1 ml-[25%] mt-2">
        <hr class="w-[35%] border-[#D6CCD5] border-2 ml-[65.4%] mt-[1%]">
        <Icon icon="mdi:circle" class="text-[#E6AC1D] text-sm" />
        <hr class="w-[35%] border-[#D6CCD5] border-2 -ml-[97.5%] mt-[1%]">
      </div>
    </div>
    <div class="grid grid-cols-2 gap-2 ml-[15%] mt-5">
      <div class="bg-[#25101F] p-10 w-[80%] text-white">
        <div class="grid grid-rows-1 grid-flow-col items-center ">
          <Icon icon="ic:round-access-time" class="text-yellow-500 text-2xl" />
          <p class="text-2xl -ml-[38%] -mt-1">Horaires d'ouverture</p>
        </div>
        <div class="mt-5">
          <div class="grid grid-rows-1 grid-flow-col items-center ">
            <Icon icon="material-symbols:location-on-rounded" class="text-yellow-500" />
            <p class="-ml-[40%]">8, Rue Corvetto - 75008 Paris</p>
          </div>
          <div class="grid grid-rows-1 grid-flow-col items-center ">
            <Icon icon="ic:round-train" class="text-yellow-500" />
            <p class="-ml-[29.5%]"> Métro : Miromesnil (ligne 9 et 13) <span
                class="rounded-[10%] bg-[#D2CB00] text-black h-[24px] w-[24px] font-bold p-[1%]">9</span>&emsp14;<span
                class="rounded-[10%] bg-[#97D5E0] text-black h-[24px] w-[24px] font-bold p-[1%]">13</span>
            </p>
          </div>
          <div class="grid grid-rows-1 grid-flow-col items-center ">
            <Icon icon="ic:baseline-directions-bus" class="text-yellow-500" />
            <p class="-ml-[28%]">Bus : 94 ( Lisbonne ou Mairie du 8ème )</p>
          </div>
          <div class="mt-5">
            <p> <span>Lundi</span> <span class="ml-[40%]">:</span> <span class="ml-[30%]">de 13h à 17h</span>
            </p>
            <p> Mardi <span class="ml-[39.7%]">:</span> <span class="ml-[30%]">de 10h à 17h</span>
            </p>
            <p> Mercredi <span class="ml-[35.7%]">:</span> <span class="ml-[30%]">de 10h à 17h</span>
            </p>
            <p> Jeudi <span class="ml-[40.5%]">:</span> <span class="ml-[30%]">de 10h à 17h</span>
            </p>
            <p> Vendredi <span class="ml-[35.7%]">:</span> <span class="ml-[30%]">de 10h à 17h</span>
            </p>
            <p> Samedi <span class="ml-[37.8%]">:</span> <span class="ml-[30%]">de 10h à 17h</span>
            </p>
            <p class="uppercase text-yellow-500 text-xl mt-5">Sur rendez-vous</p>
            <p class="mt-2">De 17h à 19h00</p>
          </div>
        </div>


      </div>
      <div>
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2623.97631560913!2d2.3124072624940375!3d48.877728049225226!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47e66fb7d205ac4f%3A0xaa97489284390c3f!2sRachat%20OR%20Paris%2C%20vendre%20OR%20Paris%2C%20bijoux%2C%20diamant%2C%20montre%20-%20Anth%C3%A9or!5e0!3m2!1sen!2sma!4v1706805828533!5m2!1sen!2sma"
          width="600" height="450" style="border:0;" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
      </div>
    </div>
    <div class="mt-[10%] text-center">
      <p class=" text-[#E0C689]">
        anthéor paris
      </p>
      <p class="text-[#362130] text-4xl font-bold ml-1">CONTACTEZ-NOUS</p>
      <div class="grid grid-cols-3 gap-1 ml-[25%] mt-2">
        <hr class="w-[35%] border-[#D6CCD5] border-2 ml-[65.4%] mt-[1%]">
        <Icon icon="mdi:circle" class="text-[#E6AC1D] text-sm" />
        <hr class="w-[35%] border-[#D6CCD5] border-2 -ml-[97.5%] mt-[1%]">
      </div>
    </div>
    <div class="grid grid-cols-4 ml-[25%] mt-5">
      <div class="bg-[#25101F] text-white p-10 text-center rounded-lg">
        <p class="uppercase text-2xl ">téléphone</p>
        <hr class="w-[20%] ml-[40%] mt-2 border-1 border-yellow-500">
        <p class="text-3xl font-semibold mt-2">01 42 89 53 18</p>
        <div class="grid grid-rows-1 grid-flow-col items-center">
          <p class="font-semibold mt-2 uppercase ml-10">étre rappelé </p>
          <Icon icon="mdi:arrow-right-thick" class="text-yellow-500 text-2xl mt-2 -ml-8" />
        </div>
      </div>
      <div class="ml-[20%] w-[150%] mt-5">
        <div class="bg-[#25101F] rounded-lg text-white rouned grid grid-rows-1 grid-flow-col items-center">
          <Icon icon="mingcute:send-plane-fill" class="bg-[#C69419] text-white text-3xl p-1 w-[40%] rounded-s-lg" />
          <p>FORMULAIRE DE CONTACT</p>
        </div>
        <div class="bg-[#25101F] rounded-lg text-white rouned mt-5 grid grid-rows-1 grid-flow-col items-center">
          <Icon icon="mdi:calendar-edit" class="bg-[#C69419] text-white text-3xl p-1 w-[40%] rounded-s-lg" />
          <p>PRENDRE RENDEZ-VOUS</p>
        </div>
        <div class=" bg-[#25101F] rounded-lg text-white rouned mt-5 grid grid-rows-1 grid-flow-col items-center">
          <Icon icon="ph:chats-circle" class="bg-[#C69419] text-white text-3xl p-1 w-[40%] rounded-s-lg" />
          <p>CHAT EN LIGNE EN DIRECT</p>
        </div>
      </div>
    </div>
    <div class="w-screen p-10 mt-10 bg-[#25101F] text-white">
      <div class="grid grid-cols-2 gap-4">
        <div>
          <div class="text-white position ml-[10%] font-bold ">
            <p class="text-xl uppercase">CONTACTEZ-NOUS</p>
            <hr class="w-[30%] border-2 border-[#D1AD60]">
          </div>
          <p class="ml-[10%] mt-2 text-xl">Besion d'un conseil ?</p>
          <p class="ml-[10%] mt-2 text-xl text-yellow-500">Une question sur l'achat de votre Or, <br>d'un bijou... ?</p>
          <p class="ml-[10%] mt-2">N'hésitez pas a nous contacter <span class="font-bold">01 42 89 53 18</span></p>
        </div>
        <div class="font-light">

          <div>
            <p>Nom (obligatoire)</p>
            <hr class="w-[30%] mt-2">
          </div>

          <div class="ml-[22%] -mt-[1.9%]  absolute">
            <p>Prenom (obligatoire)</p>
            <hr class="w-[190%] mt-2">
          </div>

          <div class="mt-[3%]">
            <p>Télephone (obligatoire)</p>
            <hr class="w-[30%] mt-2">
          </div>

          <div class="mt-5">
            <p>Message (obligatoire)</p>
            <hr class="w-[30%] mt-[7%]">
          </div>

          <div class="ml-[22%] -mt-[9%] absolute">
            <p>Email (obligatoire)</p>
            <hr class="w-[220%] mt-2">
          </div>
          <button class="bg-white rounded-lg text-black w-[20%] p-1 font-bold mt-7 ml-[35%]">Envoyer</button>
        </div>
      </div>


    </div>
    <div class="grid grid-cols-2 ml-[15%] mt-[10%]">
      <div>
        <img src="./images/img.jpg" alt="" srcset="">
      </div>
      <div class="-ml-[10%] w-[100%] text-[#240F1E]">
        <p class="text-yellow-600 uppercase">Antheor Paris</p>
        <p class="text-2xl font-bold mt-5">Antheor Paris, un comptoir spécialisé
          à votre service</p>
        <p class="mt-5 text-justify ">Depuis plus d'une vingtaine d'années d'existence, Antheor Paris s'est spécialisé
          <br>
          <span class="font-semibold">
            dans le rachat de métaux précieux à Paris tels que l'Or, le Platine ou l'Argent, sous
            toutes leurs formes, qu'ils soient en lingots, en bijoux ou encore en pièces de
            monnaie. Mais encore, le comptoir peut également vous racheter vos objets
            d'antiquité de valeur.</span> <br>
          <span>
            Si vous avez investi dans des bijoux précieux et autres objets antiques pour protéger
            et diversifier vos épargnes, les revendre constitue également un meilleur moyen
            d'obtenir rapidement des liquidités. Antheor Paris vous fait bénéficier des meilleurs
            coûts du marché, vous pouvez vendre à partir d'un gramme, et proposez vos propres
            prix selon vos besoins et vos envies. Avec Antheor Paris, vous serez payé au comptant,
            aux meilleurs prix. </span><br>
          GRACHAT OR ET ARGENT: NOUS VOUS ACHETONS VOS
          BIENS AUX MEILLEURS PRIX
          La Pépinière
          Antheor Paris est l'un des acteurs incontournables du marché des métaux précieux à
          Paris. Nombreux sont ceux qui nous ont déjà fait confiance, nous avons déjà pu
          satisfaire différents vendeurs avec des cours extrêmement compétitifs.
        </p>
      </div>
      <div class="bg-[#C69419] text-white mt-10 w-[195%] p-5">
        <p class="font-bold">RACHAT DE BIJOUX: SECURITE ET CONFIDENTIALITE SONT DE MISES</p>
        <div class="mt-10">
          <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Autem necessitatibus reprehenderit veritatis sed
            nisi
            vero eveniet ipsum voluptatem, et, quas nulla corrupti molestias, accusantium fugit porro atque dolore
            sapiente
            ipsa?</p>
          <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis quaerat porro odit voluptas ut quia
            earum accusamus numquam fugit neque eveniet sint praesentium tenetur possimus aliquam dolorem odio, molestias
            et.</p>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cumque ducimus numquam repellat hic aspernatur
            facere,
            voluptatem quidem reiciendis beatae quam fuga sed est molestias, consectetur voluptates iusto. Necessitatibus,
            dolorem porro.</p>
        </div>
      </div>
    </div>
    <div class="w-screen p-10 mt-10 bg-[#25101F] text-white">
      <div class="grid grid-cols-3 gap-3 text-center text-xl">
        <div>
          <Icon icon="ph:chats-circle-bold" class="text-yellow-500 text-4xl ml-[46%]" />
          <p class="mt-5">Besion de conseils ? n'hésitez pas a <br> nous contacter</p>
        </div>
        <div>
          <Icon icon="material-symbols:call" class="text-yellow-500 text-4xl ml-[46%]" />

          <p class="mt-5">Vous souhaitez vendre de l'or ? faites <br> appel a un specialiste de rachat</p>
        </div>
        <div>
          <Icon icon="ic:baseline-shield" class="text-yellow-500 text-4xl ml-[46%]" />

          <p class="mt-5">Réalizes vos transactions en toute <br> sécuriter et en toute discrétion</p>
        </div>

      </div>


    </div>
    <div class="grid grid-cols-2 text-[#2F1C2A] ml-[15%] mt-10 ">
      <div class="bg-white p-5 w-[87%] h-[60%] drop-shadow-xl">
        <p class="text-xl font-bold ml-2">Voila maintenat <span class="text-yellow-500 text-2xl">plus de 20 ans
          </span>que notre comptoir <br>
          spécialisé anthéor est présent sur le marché.
          depuis
          plus de 20 ans .
        </p>
        <p class="mt-[10%] ml-5 text-xl">N'hésitez pas a faire appel au spécialiste de l'achat et de <br> la vente d'Or
          <span class="font-bold">numéro
            1 a
            Paris</span>
        </p>
        <p class="mt-[10%] ml-5 text-xl">Nous vous conseillons <span class="font-bold">gratuitement</span> et en toute
          <br>
          <span class="font-bold">discrétion</span> . Des millier de clients nous font confiance . <br> faites comme eux !
        </p>
      </div>
      <div>
        <img src="./images/img.jpg" class="-ml-[10%]" alt="">
      </div>
      <div class="-mt-[35%]">
        <p class="absolute text-white font-regular text-center w-[36.9%] pt-[5%] text-2xl font-light">
          CONTACTEZ-NOUS <br>
          01 42 89 53 18 <br>
          contact@antheor-paris.fr
        </p>

        <img src="./images/L00011.jpg" alt="">

      </div>
    </div>
    <div class="mt-[9%] text-center">
      <p class="uppercase text-[#E0C689]">
        anthéor paris
      </p>
      <p class="text-[#362130] text-4xl font-semibold ml-1">Ils parlent De Nous</p>
      <div class="grid grid-cols-3 gap-1 ml-[25%] mt-2">
        <hr class="w-[35%] border-[#D6CCD5] border-2 ml-[65.4%] mt-[1%]">
        <Icon icon="mdi:circle" class="text-[#E6AC1D] text-sm" />
        <hr class="w-[35%] border-[#D6CCD5] border-2 -ml-[97.5%] mt-[1%]">
      </div>
    </div>
    <div class="grid grid-cols-2 mt-5">
      <div class="max-w-md mx-auto bg-white rounded-xl shadow-md overflow-hidden md:max-w-2xl">
        <div class="md:flex">
          <div class="md:shrink-0">
            <img class="h-48 w-full object-cover md:h-full md:w-48" src="./images/img.jpg"
              alt="Modern building architecture">
          </div>
          <div class="p-8">
            <div class="uppercase tracking-wide text-sm text-indigo-500 font-semibold">Company retreats</div>
            <a href="#" class="block mt-1 text-lg leading-tight font-medium text-black hover:underline">Incredible
              accommodation for your team</a>
            <p class="mt-2 text-slate-500">Looking to take your team away on a retreat to enjoy awesome food and take in
              some sunshine? We have a list of places to do just that.</p>
          </div>
        </div>
      </div>
      <div class="max-w-md mx-auto bg-white rounded-xl shadow-md overflow-hidden md:max-w-2xl">
        <div class="md:flex">
          <div class="md:shrink-0">
            <img class="h-48 w-full object-cover md:h-full md:w-48" src="./images/img.jpg"
              alt="Modern building architecture">
          </div>
          <div class="p-8">
            <div class="uppercase tracking-wide text-sm text-indigo-500 font-semibold">Company retreats</div>
            <a href="#" class="block mt-1 text-lg leading-tight font-medium text-black hover:underline">Incredible
              accommodation for your team</a>
            <p class="mt-2 text-slate-500">Looking to take your team away on a retreat to enjoy awesome food and take in
              some sunshine? We have a list of places to do just that.</p>
          </div>
        </div>
      </div>
    </div>
    <div class="w-screen p-10 mt-10 bg-[#25101F] text-white">
      <div class="grid grid-cols-3 gap-3 text-center text-xl">
        <div>
          <img src="./images/logo-footer.png" class="ml-[25%]" alt="" srcset="">
        </div>

        <div class="grid grid-cols-2 font-light">
          <p class="uppercase">Lien Utiles</p>
          <hr class="absolute w-[2%] mt-8 ml-[5%] border-yellow-500 border-2">
          <div class="absolute mt-[5%] ml-[5%]">
            <p> > Rachat Or</p>
            <p> > Diamants</p>
            <p> > Argenterie</p>
          </div>
          <div class="mt-[30%] ml-[5%]">
            <p> > Mention légales</p>
            <p> > Politique de confidentialité</p>
            <p> > Contact</p>
          </div>
        </div>
        <div class="grid grid-cols-2 font-light">
          <p class="uppercase">Info</p>
          <hr class="absolute w-[2%] mt-8 ml-[6.7%] border-yellow-500 border-2">
          <div class="absolute mt-[5%] ml-[6.7%]">
            <div class="grid grid-rows-1 grid-flow-col items-center">
              <Icon icon="material-symbols:call" class="text-yellow-500" />
              <p class="-ml-[125%]"> 01 42 89 53 18 </p>
            </div>
            <div class="grid grid-rows-1 grid-flow-col items-center">
              <Icon icon="material-symbols:android-messages" class="text-yellow-500" />
              <p class="-ml-[55%]"> contact@antheor-paris.fr</p>
            </div>
            <div class="grid grid-rows-1 grid-flow-col items-center">
              <Icon icon="material-symbols:add-location" class="text-yellow-500" />
              <p class="ml-5"> 8, Rue Corvetto 75008, Paris FRANCE</p>

            </div>
          </div>

        </div>

      </div>



    </div>
    <div class="bg-[#1D0D18] w-screen text-white">
      <div class="grid grid-cols-2 gap-2">
        <div>
          <p class="text-light text-sm ml-[10%] p-5">Copyright www.antheor-paris.fr 2016-2021 - All rights reserved - Tous
            droits
            réservés
          </p>
        </div>
        <div class="grid grid-rows-1 grid-flow-col items-center">
          <p class="text-light text-sm ml-[30%] p-5">Dévelopment & Référance naturel par
          </p>
          <img src="./images/logo-ed.png" alt="">
        </div>

      </div>
    </div>
  </div>
</template>
<script setup>
import { Icon } from '@iconify/vue';
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import { Disclosure, DisclosureButton, DisclosurePanel, Menu, MenuButton, MenuItem, MenuItems } from '@headlessui/vue'
import { Bars3Icon, BellIcon, XMarkIcon } from '@heroicons/vue/24/outline'
const navigation = [
  { name: 'Accueil', href: '#', current: true },
  { name: 'Rachat Or', href: '#', current: false },
  { name: 'Argent', href: '#', current: false },
  { name: 'Argenterie', href: '#', current: false },
  { name: 'Bijoux', href: '#', current: false },
  { name: 'Antiquités', href: '#', current: false },
  { name: 'Diamants', href: '#', current: false },
  { name: 'Montres', href: '#', current: false },
  { name: 'Tableaux', href: '#', current: false },
  { name: 'Contact', href: '#', current: false },
  { name: 'Plan d\'accés', href: '#', current: false },
  { name: 'Qui sommes-nous', href: '#', current: false },
  { name: 'Blog', href: '#', current: false },



]
</script>
<style>
h1 {
  font-family: 'Italianno';
}

.carousel__item {
  min-height: 200px;
  width: 100%;
  background-color: var(--vc-clr-primary);
  color: var(--vc-clr-white);
  font-size: 20px;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.carousel__slide {
  padding: 10px;
}

.carousel__prev,
.carousel__next {
  box-sizing: content-box;
}

style>.carousel__item {
  min-height: 200px;
  width: 100%;
  background-color: var(--vc-clr-primary);
  color: var(--vc-clr-white);
  font-size: 20px;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.carousel__slide {
  padding: 10px;
}

.carousel__prev,
.carousel__next {
  box-sizing: content-box;
  border: 1px solid white;
  border-radius: 100%;
  height: 50px;
  width: 50px;
  margin-left: 80px;
  margin-right: 80px;
  background-color: #2E2B24;
  color: white;
}

.carousel__prev :hover,
.carousel__next :hover {
  color: white;
}
</style>