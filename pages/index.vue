<template>
 <div>
   <input
                ref="codeInput"
                type="number"
                v-model="form.password"
                placeholder="●●●●●●"
                min="1"
                @keyup.enter="onSubmit"
                @input="onInput"
              />
   </div>
</template>

<script>
export default {
  name: 'IndexPage',
   data() {
    return {
      currentLang: 1,
      langList: [
        {
          name: "Uzb",
          icon: "uzbFlag",
          id: 1,
          code: "uz",
        },
        {
          name: "Rus",
          icon: "rusFlag",
          id: 3,
          code: "ru",
        },
      ],

      other: "",
      timeProgress: 100,
      smsError: false,
      loadingBtn: false,
      isLoading: false,
      time: 0,
      form: {
        phone_number: "",
        password: "",
      },
      rules: {
        password: [
          {
            required: true,
            message: "Kod 6 xonali bo'lishi kerak",
            trigger: "change",
          },
          { min: 6, message: "Kod 6 xonali bo'lishi kerak", trigger: "change" },
        ],
      },
    };
  },
   methods: {
    onInput() {
    if (this.form.password && this.form.password.toString().length > 6) {
      this.form.password = parseInt(this.form.password.toString().slice(0, 6));
    }
       onSubmit() {
     
    },
  },
   }
}
</script>
