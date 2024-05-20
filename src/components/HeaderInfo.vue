<template>
    <div class="header__info">
      <div class="container">
        <div class="header__info-flex">
          <div class="header__info-left">
              <p class="header__info-descr">Empowering entreprenerus to launch their own trading systems.</p>
          </div>
          <div class="header__info-right">
            <a href="#" class="header__info-link">
              <SvgIcon name="phone"/>
              8 888 888 88 88
            </a>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import SvgIcon from './SvgIcon.vue'

  export default {
    name: 'HeaderInfo',
    components: {
      SvgIcon
    }
  }
  </script>
  
  <style scoped lang="scss">
  .header__info {
    padding-top: 22px;
    padding-bottom: 22px;
    .header__info-flex {
      display: flex;
      justify-content: space-between;
      .header__info-left {
        text-align: left;
        max-width: 50%;
        .header__info-descr {
          font-family: "Roboto", sans-serif;
          font-size: 16px;
          line-height: 19px;
          font-weight: 400;
          color: #000000;
          margin: 0;
          @media (max-width: 520px) {
            font-size: 12px;
            line-height: 14px;
            color: #9F9F9F;
          }
        }
      }
      .header__info-right {
        .header__info-link {
          font-family: "Roboto", sans-serif;
          font-size: 16px;
          line-height: 19px;
          font-weight: 400;
          text-decoration: none;
          color: #000000;
            svg {
              transform: translate(-7px, 7px);
            } 
        }
      }
    }
  }
  </style>
  