<template>
  <h1 id="judul">FORM SEDERHANA</h1>
  <form @submit.prevent="handleSubmit">
        <!-- pada form ini, requirement untuk isi datanya tidak saya buat karna emang tidak diperlukan -->
        <!-- jadi bisa saja data di submit walaupun kosong -->
        <label>Nama : </label>
        <input type="text" placeholder="Masukkan nama" v-model="nama"/>
        <br/>
        <label>Jenis kelamin : </label>
        <select v-model="gender" id="check">
            <option value="Pria">Pria</option>
            <option value="Wanita">Wanita</option>
        </select>
        <br/><br>
        <label>Alamat : </label>
        <input type="text" placeholder="Masukkan alamat" v-model="alamat"/>
        <label>Email : </label>
        <input type="text" placeholder="@ Masukkan email" v-model="email"/>
        <label>No Telp : </label>
        <input type="text" placeholder="Masukkan nomor telepon" v-model="noHP"/>
        <label>Agama : </label>
        <select v-model="agama" id="check">
            <option value="Islam">Islam</option>
            <option value="Kristen">Kristen Protestan</option>
            <option value="Katolik">Katolik</option>
            <option value="Budha">Budha</option>
            <option value="Hindu">Hindu</option>
            <option value="Konghucu">Konghucu</option>
        </select>
        <div class="submit">
            <button v-on:click="show">Submit</button>
        </div>
  </form>
  <div id="content">
    <h2>Data Anda</h2>
    <p> Nama &ensp; &ensp; &ensp; &ensp; &ensp; : {{ nama }} </p>
    <p> Jenis kelamin&ensp; : {{ gender }} </p>
    <p> Alamat &ensp; &ensp; &ensp; &ensp; : {{ alamat }} </p>
    <p> Email &ensp; &ensp; &ensp; &ensp; &ensp; : {{ email }} </p>
    <p> No Telp &ensp; &ensp; &ensp; &ensp; : {{ noHP }} </p>
    <p> Agama &ensp; &ensp; &ensp; &ensp; &ensp;: {{ agama }} </p>
  </div>
  
</template>

<script>
export default {
    data() {
        return {
                nama: '',
                // Sengaja saya buat pilihan utamanya adalah pria, biar yang diampilnkan tidak kosong
                gender: 'Pria',
                alamat: '',
                email: '',
                noHP: '',
                // ini pun sama, jadi agama Islam terpilih otomatis
                agama : 'Islam'
            }
        },
    methods: {
        handleSubmit() {
            console.log('form.submited')
        },
        show(){
            document.getElementById('content').style.display="block"
        }
    }
}
</script>

<style>
    @import "https://use.fontawesome.com/releases/v5.5.0/css/all/.css";

    #judul {
        color: white;
        text-align: center;
    }
    form {
        max-width: 65%; margin: 30px auto;
        justify-content: center;
    }
    label {
        color: rgb(255, 255, 255);
        display: inline-block;
        margin: 10px 0 10px;
        font-size: 0.9em;
        text-transform: uppercase; letter-spacing: 1px;
        font-weight: bold;
    }
    input, select {
        display: block;
        height: 40px;
        border: none;
        padding: 10px 6px;
        width: 100%;
        box-sizing: border-box;
        border-radius: 1em;
        color: white;
        background: rgba(255, 255, 255, 0.1);
        outline: none;
    }
    ::-webkit-input-placeholder{
        color: white;
    }
    #check {
        color: rgb(255, 255, 255);  
        background-color: rgba(1, 50, 39, 0.712);
    }
    button {
        background: #03542d;
        border: 0;
        padding: 10px 20px;
        margin-top: 20px;
        color: white;
        border-radius: 20px;
        font-size: 0.9em;
    }
    .submit {
        text-align: center;
    }
    #content {
        max-width: 65%; margin: 15px auto;
        background: rgb(219, 219, 219);
        text-align: left;
        padding: 40px; 
        border-radius: 10px;
        display: block;
        border: none;
        padding: 10px 6px;
        width: 100%;
        box-sizing: border-box;
        border-radius: 1em;
        color: white;
        background: rgba(255, 255, 255, 0.1);
        outline: none;
    }
    #content {
        display: none;
        display: 0px;
    }

</style>