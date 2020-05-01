<template>
    <div class="formContainer">
        <form>
            <h1>Get in touch</h1>
            <input type="text" class="info" id="name" placeholder="Name">
            <input type="email" class="info" id="email" placeholder="Email">
            <textarea id="message" class="info" cols="30" rows="10" placeholder="Message"></textarea>
            <button class="btnForm" value="send">Send</button>
        </form>
    </div>
</template>
<script>
export default {
  name: 'FormContact'
}
</script>
<style scoped>
    h1 {
        text-align: center;
    }

    .formContainer {
        display: flex;
        width: 100%;
        justify-content: center;
        align-items: center;
    }

    form {
        display: flex;
        flex-flow: column;
        background: white;
        width: 100%;
        height: 80%;
        padding: 20px;
        justify-content: center;
        align-items: center;
    }

    .info {
        border: none;
        resize: none;
        outline: none;
        padding: 15px 0;
        width: 80%;
        margin: 20px;
        transition: all 300ms;
        border-bottom: 1px solid rgba(0, 0, 0, 0.2);
    }

    .info:focus {
        border-bottom: #610061;
    }

    .btnForm {
        padding: 0;
        font-size: 0.8em;
        margin: 0;
        width: 30%;
        height:30px;
        border: none;
        outline: none;
        background: #413968;
        color: #fff;
        border-radius: 2px;
        cursor: pointer;
        transition: all 300ms;
    }

    .btnForm:hover {
        background: #50467e;
    }
</style>
