<template>
      <section >
          <div id="title">
              <img src="../../assets/pokeball.png" alt="logo">
              <span>Pokédex</span>
          </div>
  
          <div class="filter">
              <div class="search-bar">
               <div id="search-icon">
                  <Icon  icon="ic:outline-search"/>
               </div>
              <input
              type="text" 
              id="search-input" placeholder='Search '
              v-model="name"
              />
  
              <div @click="() => name=''" class="close-icon" :class="{show : name}">
                  <Icon icon="material-symbols:close"/>
              </div>
              
              </div>
  
              <div class="menu">
                  <Icon icon="iconoir:menu-scale"/>
              </div>
  
          </div>
      </section>
  </template>
  
  <script setup>
      import { Icon } from '@iconify/vue';
      import { ref } from 'vue'

      const name = ref('');
  </script>
  
  <style scoped>
  
      section{
        display: flex;
        flex-direction: column;
        gap: 8px;
        padding: 12px 12px 24px 12px;
        
      }
  
      #title{
          display: flex;
          align-items: center;
          gap: 16px;
      }
  
      #title span{
          color: white;
          font-size: 24px;
          font-weight: 700;
      }
  
      .filter{
          display: flex;
          align-items: center;
          gap: 16px;
      }
  
      .menu{
          background-color: white;
          display: flex;
          align-items: center;
          justify-content: center;
          padding: 8px;
          width: 32px;
          height: 32px;
          border-radius: 100%;
      }
  
      .search-bar {
          flex-grow: 1;
          display: flex;
          align-items: center;
          gap: 8px;
          padding: 8px 16px;
          background-color: white;
          box-shadow: inset 0px 1px 3px 1px rgba(0, 0, 0, 0.25);
          border-radius: 16px;
  
      }
  
      svg{
          height: 16px;
          width: 16px;
          color: red;
          display: flex;
          align-items: center;
      }

      .close-icon{
        cursor: pointer;
        opacity: 0;
      }

      .show{
        opacity: 1;
      }
  
      #search-input {
          flex-grow: 1;
          outline: none;
          border: none;
          color: black;
      }
  
      @media screen and (min-width: 768px) {

        section{
            flex-direction: row;
            align-items: center;
            justify-content: space-between;
        }

        #title span{
            font-size: 35px;
        }

        #search-input {
            font-size: 18px;
        }

        .search-bar svg{
            height: 20px;
            width: 20px;
        }

      }  </style>
  