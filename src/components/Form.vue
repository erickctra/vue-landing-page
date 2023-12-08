<script setup>

</script>

<template>
  <div class="p-4 bg-white flex-1 rounded-lg text-neutral-700 flex flex-col gap-y-3 w-full basis-[22rem]  shadow-2xl">
    <h1 class="mt-4 text-3xl font-medium max-w-sm text-center mx-auto">ENCONTRE SEU NOVO ESTILO DE VIDA</h1>
    <p class="max-w-sm text-center mx-auto">Preencha o formulário abaixo para receber todas as informações sobre
      imóveis disponiveis</p>
    <form action="" method="post" @submit.prevent="submitHandler">
      <label class="flex flex-col text-sm leading-6 text-neutral-700" for="name">
        Nome*
        <input id="name" v-model="form.name"
          class="block w-full bg-transparent outline-0 h-[3.75rem] rounded-md border-0 py-1.5 px-4 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-emerald-900 sm:text-sm sm:leading-6"
          type="text" name="name" placeholder="Digite seu Nome">
      </label>
      <label class="flex flex-col text-sm leading-6 text-neutral-700" for="tel">
        Telefone*
        <input id="tel" v-model="form.number"
          class="block w-full bg-transparent outline-0 h-[3.75rem] rounded-md border-0 py-1.5 px-4 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-emerald-900 sm:text-sm sm:leading-6"
          type="text" name="tel" min={1111111111} required placeholder="Digite seu Telefone">
      </label>
      <label class="flex flex-col text-sm leading-6 text-neutral-700" for="whatsapp">
        Whatsapp*
        <input id="whatsapp" v-model="form.whatsapp"
          class="block w-full bg-transparent outline-0 h-[3.75rem] rounded-md border-0 py-1.5 px-4 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-emerald-900 sm:text-sm sm:leading-6"
          type="text" name="tel" min={1111111111} required placeholder="Digite seu WhatsApp">
      </label>

      <div class="flex flex-row flex-wrap gap-3">
        <label class="flex flex-col flex-1 basis-44 text-sm leading-6 text-neutral-700 " for="rooms">
          Quantidade de Quartos*
          <input id="rooms" v-model="form.quartos"
            class="block w-full bg-transparent outline-0 h-[3.75rem] rounded-md border-0 py-1.5 px-4 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-emerald-900 sm:text-sm sm:leading-6"
            min={1} minlength="1" max={8} type="number" name="whatsapp" required placeholder="2 dorms">
        </label>

        <label class="flex flex-col flex-1 basis-44 text-sm leading-6 text-neutral-700" for="whatsapp">
          Zona*
          <select v-model="form.regiao"
            class="block w-full bg-transparent outline-0 h-[3.75rem] rounded-md border-0 py-1.5 px-4 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-emerald-900 sm:text-sm sm:leading-6"
            name="" required>
            <option disabled value="">Selecione uma Zona</option>
            <option value="Zona Norte">Zona Norte</option>
            <option value="Zona Leste">Zona Leste</option>
            <option value="Zona Sul">Zona Sul</option>
            <option value="Centro">Centro</option>
            <option value="Zona Oeste">Zona Oeste</option>
          </select>
        </label>
      </div>

      <div class="flex flex-row gap-3 mt-2">
        <div class="flex items-center gap-x-3">
          <input id="push-everything" name="push-notifications" v-model="form.garagem" value="Sem garagem" required
            type="radio" class="h-4 w-4 border-gray-300 text-indigo-600 focus:ring-indigo-600">
          <label for="push-everything" class="block text-sm leading-6 text-gray-900">Sem Garagem</label>
        </div>
        <div class="flex items-center gap-x-3">
          <input id="push-email" name="push-notifications" v-model="form.garagem" value="Com gargem" required type="radio"
            class="h-4 w-4 border-gray-300 text-indigo-600 focus:ring-indigo-600">
          <label for="push-email" class="block text-sm leading-6 text-gray-900">Com Garagem</label>
        </div>
      </div>
      <hr class="h-px my-2 bg-gray-300 border-0">
      <p class="text-sm">Ao completar o formulário, você está concordando em ser contatado exclusivamente por Eliana
        Dantas, atuando pelo CRECISP - 254502-F para discutir nosso produto. Valorizamos sua privacidade e usaremos
        suas informações apenas para fornecer informações relevantes sobre nossos produtos e serviços, adaptados às
        suas necessidades.</p>
      <button type="submit"
        class="text-white mt-2 w-full h-[3.75rem] bg-neutral-800 hover:bg-neutral-900 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5  dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800">
        Receber mais informações
      </button>
    </form>
    <small class="mx-auto">ou</small>
    <a target="_blank"
      href="https://api.whatsapp.com/send?phone=5511996048780&text=Ol%C3%A1%2C%20gostaria%20de%20falar%20sobre%20um%20dos%20imoveis%20em%20seu%20site"
      class="text-[#1A1C18] text-center flex items-center justify-center w-full h-16 py-2 px-6 bg-[#9CD67D] hover:bg-[#80A86A] focus:ring-4 focus:ring-[#B8E2A1] font-medium rounded-lg text-sm">
      Contato por WhatsApp
    </a>
  </div>
</template>
<style scoped></style>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        number: '',
        whatsapp: '',
        quartos: 0,
        regiao: '',
        garagem: '',
      }
    }
  },
  methods: {
    submitHandler() {
      // event.preventDefault();
      const config = {
        SecureToken: "052e237b-9b2c-4bd3-84ca-8c0dec63ef47",
        To: 'licaa.dantas@gmail.com',
        From: "contato@elianadantascorretora.com.br",
        Subject: "Você recebeu um contato de seu site",
        Body: `Informações de contato:
            <br/>
            <hr/>
            <p>Nome do solicitante: ${this.form.name}</p>
            <p>Numero: ${this.form.number}</p>
            <p>Numero do whatsapp: ${this.form.whatsapp}</p>
            <p>Região de interesse: ${this.form.regiao}</p>
            <p>Garagem: ${this.form.garagem}</p>
            <p></p>`
      }


      if (window.Email) {
        window.Email.send(config).then(
          window.open("https://elianadantascorretora.com.br/ok", '_blank')
        );
      }
    }
  }
}
</script>