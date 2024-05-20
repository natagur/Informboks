<template>
    <div class="header__menu">
      <div class="container">
        <div class="header__menu-flex">
          <div class="header__menu-logo">
            <SvgIcon name="logo"/>
          </div>
          <nav v-bind:class="'header__nav' + (openBurger ? ' active' : '')">
            <ul class="header__nav-list">
              <li class="header__nav-item"
                v-for="(link, index) in links" :key="index">
                <a class="header__nav-link" @click="emitId(index)">{{ link }}</a>
              </li>
            </ul>
          </nav>
          <SvgIcon class="header__burger" name="burger" @click="handleBurger()"/>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import SvgIcon from './SvgIcon.vue'

  export default {
    name: 'HeaderMenu',
    components: {
      SvgIcon
    },
    data: function(){
      return {
        links: [
          'Classic Brokerage MT4 | MT5',
          'Margin World Class Exchange',
          'Crypto World Class Exchange',
          'Financial Licensing',
        ],
        openBurger: false
      }
    },
    methods: {
      emitId(linkId) {
        this.openBurger = false;
        this.$emit('idClicked', linkId);
      },
      handleBurger() {
        this.openBurger = !this.openBurger;
      }
    }
  }
  </script>
  
  <style scoped lang="scss">
  .header__menu {
    background: #547966;
    box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
    margin-bottom: 123px;
    .header__menu-flex {
      padding-top: 15px;
      padding-bottom: 15px;
      display: flex;
      justify-content: space-between;
      .header__menu-logo {
        margin-right: 68px;
        @media (max-width: 1020px) {
          margin-right: 0;
        }
      }
      .header__nav {
        width: 100%;
        .header__nav-list {
          list-style-type: none;
          padding: 0;
          margin: 0;
          display: flex;
          justify-content: space-between;
          width: 100%;
          .header__nav-item {
            margin-right: 10px;
            &:last-child {
              margin-right: 0;
            }
            .header__nav-link {
              font-size: 18px;
              line-height: 22px;
              font-weight: 700;
              color: #fff;
              cursor: pointer;
            }
          }
        }
        @media (max-width: 1020px) {
          display: none;
          &.active {
            display: block;
            .header__nav-list {
              flex-direction: column;
              gap: 20px;
            }
          }
        }
      }
      .header__burger {
        display: none;
        @media (max-width: 1020px) {
          display: block;
        }
      }
    }
    @media (max-width: 520px) {
      margin-bottom: 34px;
    }
  }
  </style>
  