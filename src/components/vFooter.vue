<template>
  <div class="footer">
    <div class="container">
      <div class="footer__wrapper">
        <ul class="footer__list">
          <a href="#"><li class="footer__item">Каталог</li></a>
          <a href="#"><li class="footer__item">Доставка</li></a>
          <a href="#"><li class="footer__item">Оплата</li></a>
          <a href="#"><li class="footer__item">Контакты</li></a>
          <a href="#"><li class="footer__item">О компании</li></a>
        </ul>
        <div class="footer__info">
          <div class="footer__phone-box">
            <img
              src="@/assets/images/icons/phone.svg"
              alt="icon-phone"
              class="footer__phone-img"
            />
            <a href="tel:+78125555555" class="footer__tel"
              >+7 (812) 555-55-55</a
            >
          </div>
          <div class="footer__adress-box">
            <img
              src="@/assets/images/icons/adress.svg"
              alt="icon-adress"
              class="footer__adress-img"
            />
            <a
              href="https://goo.gl/maps/z5DHh2vuPhLPKG8i6"
              target="_blank"
              rel="noopener noreferrer"
              class="footer__adress"
              >г. Санкт-Петербург, ул. Ефимова, 3</a
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style lang="scss" scoped>
.container {
  width: 1200px;
  margin: 0 auto;
}
.footer {
  background: #eceaea;
  padding: 38px 20px;
  &__wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  &__list {
    display: flex;
    justify-content: space-between;
  }
  &__item {
    font-weight: 400;
    font-size: 14px;
    line-height: 150%;
    color: #555555;
    margin-right: 48px;
  }
  &__info {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  &__tel {
    font-weight: 400;
    font-size: 14px;
    line-height: 150%;
    color: #555555;
    margin-right: 55px;
  }
  &__adress {
    font-weight: 400;
    font-size: 14px;
    line-height: 150%;
    color: #555555;
  }
  &__phone-box {
    display: flex;
    align-items: center;
  }
  &__adress-box {
    display: flex;
    align-items: center;
  }
  &__phone-img {
    margin-right: 10px;
  }
  &__adress-img {
    margin-right: 10px;
  }
}
.footer__list:last-child {
  margin-right: 0;
}
@media (max-width: 1300px) {
  .footer {
    &__list {
      display: block;
    }
    &__info {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
  }
}
</style>
