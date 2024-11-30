<script setup>
//aqui teremos a lógica
//função, imports, variáveis
import {ref} from "vue";
import coracao from "./assets/coracao.png";
import curtido from "./assets/curtido.png";

const isCurtido1 = ref(false);
const isCurtido2 = ref(false);
const isCurtido3 = ref(false);


const toggleCurtida1 = () => {
  isCurtido1.value = !isCurtido1.value;
};

const toggleCurtida2 = () => {
  isCurtido2.value = !isCurtido2.value;
};

const toggleCurtida3 = () => {
  isCurtido3.value = !isCurtido3.value;
};

</script>

<template>
  <!--tags, ou seja tudo que será renderizado na tela-->
  <header>
    <h1>Code<span> Lab. </span> Vue</h1>
    <input type="text" placeholder="Pesquisar no blog ">
  </header>
  <main>
    <section class="divisao">
      <div>
        <p class="data">17 de ago, 2024</p>
        <!--para renderizar um dado da lógica, se for em uma tag usaremos chaves duplas {{  }} exemplo da tag P
        para renderizar dentro de atributos, nós vamos usar o v-bind que é a ligação entre a logica e a tag, o atalho para o v-bind que será usado que são os :
        -->
        <img 
          :src="isCurtido1 ? curtido : coracao" 
          alt="Imagem de um Coração" 
          @click="toggleCurtida1" 
        >
      </div>
      <h3 class="Titulo">Vue.js: O Framework Progressivo que Ganhou o Mundo</h3>
      <p class="texto">Vue.js foi criado por Evan You em 2014 enquanto trabalhava no Google. Ele queria combinar as melhores ideias de frameworks como Angular e React em uma ferramenta mais leve e simples de usar. Hoje, Vue é amplamente utilizado, especialmente na Ásia, onde é o framework de escolha em muitas empresas de tecnologia.</p>
    </section>
    <section class="divisao">
      <div>
        <p class="data">12 de jul, 2024</p>
        <img 
          :src="isCurtido2 ? curtido : coracao" 
          alt="Imagem de um Coração" 
          @click="toggleCurtida2" >
      </div>
      <h3 class="Titulo">Uma Biblioteca Pequena com Impacto Gigante</h3>
      <p class="texto">Um dos diferenciais do Vue é sua flexibilidade. Diferente de outros frameworks, ele pode ser usado tanto para pequenas melhorias em projetos existentes quanto para construir aplicativos completos do zero. Além disso, seu tamanho compacto (apenas cerca de 20 KB) o torna extremamente rápido para carregar.</p>
    </section>
    <section class="divisao">
      <div>
        <p class="data">30 de nov, 2024</p>
        <img 
          :src="isCurtido3 ? curtido : coracao" 
          alt="Imagem de um Coração" 
          @click="toggleCurtida3" 
        >
      </div>
      <h3 class="Titulo">Intuitivo, Poderoso e Amado pela Comunidade</h3>
      <p class="texto">A comunidade Vue é uma das mais acolhedoras no mundo do desenvolvimento web. O framework conta com uma excelente documentação oficial, que foi traduzida para diversos idiomas pela própria comunidade, tornando-o acessível a desenvolvedores iniciantes e experientes ao redor do mundo.</p>
    </section>
  </main>
  
</template>

<style scoped lang="scss">
/*todo o estilo da página */
/*a tecnologia que será usada precisa ser informada, para que o estilo funcione, por isso tem que usar o lang */
header{
  background-color: #17171A;
  color: #e07b67;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  padding: 20px;
}
main{
  background: #121214;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  height: auto;
  padding: 30px;
  line-height: 40px;
  
}
.divisao{
  padding: 30px;
  line-height: 40px;
}
h1{
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 500;
  font-size: 40;
  height: 183px;
  
  
  
  span{
    color: #FFFFFF;

  }
}
input{
  width: 65%;
  height: 50px;
  margin-top: 0;
  display: flex;
  border-radius: 4px;
  justify-content: space-evenly;
  margin-top: -40px;
  margin-bottom: 20px;
  border: 2px solid #252529;
  background: #202024;
  padding: 10px;
  &::placeholder{
    font-family: "Inter", sans-serif;
    font-weight: 500;
    font-size: 20px;
    color: #AFABB6;

  }

}
.data{
  color: #E07B67;
  font-family: "Inter", sans-serif;
  font-weight: 500;
  font-size: 16px;

}
section{
  display: flex;
  width: 65%;
  flex-direction: column;
  border: 2px solid #252529;
  border-radius: 6px;
  margin: 20px 30px;
  &:hover{
    border: 2px solid #E07B67;
  }
}
div{
  display: flex; 
  flex-direction: row; 
  width: 100%;
  height: 60px;
  justify-content: space-between; 
  align-items: center; 
}
.Titulo{
  font-family: "Space Grotesk", sans-serif;
  color: #FFFFFF;
  font-weight: 500;
  font-size: 24px;

}
img{
  display: flex;
  flex-direction: row;
  align-items: flex-end;
  cursor: pointer;
        transition: 0.5s ease-in-out;

        &:hover {
          transform: scale(1.2);
        }
}
.texto{
  font-family: "Inter", sans-serif;
  color: #AFABB6;
  font-weight: 500;
  font-size: 20px;

}
</style>
