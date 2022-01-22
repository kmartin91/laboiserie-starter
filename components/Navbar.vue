<template>
  <div class="header">
    <div class="header__logo">
      <strong>LOGO</strong>
    </div>
    <nav class="navbar">
      <ul class="navbar__menu">
        <li class="navbar__item">
          <a href="#" class="navbar__link"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
          </svg><span>Vêtements</span> </a>
        </li>
        <li class="navbar__item">
          <a href="#" class="navbar__link"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
          </svg><span>Accessoires</span></a>
        </li>
        <li class="navbar__item">
          <a href="#" class="navbar__link"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
          </svg><span>Stickers</span></a>
        </li>
        <li class="navbar__item">
          <a href="#" class="navbar__link"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
          </svg><span>Montres</span></a>
        </li>
        <li class="navbar__item">
          <a href="#" class="navbar__link"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
          </svg><span>Draisiennes</span></a>
        </li>
        <li class="navbar__item">
          <a href="#" class="navbar__link"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
          </svg><span>Cross</span></a>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  mounted() {
    // feather.replace()
  }
}
</script>

<style lang="scss">
$borderRadius: 10px;
$spacer: 1rem;
$primary: #C4151C;
$text: #fff;
$linkHeight: $spacer * 3.5;
$timing: 250ms;
$transition: $timing ease all;
$linkWidth: 10rem;

@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@600&display=swap');

.header {
  $ref: &;
  position: sticky;
  top: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.9);
  color: $text;
  padding: 0 $spacer*2;
  box-shadow: 0 0 40px rgba(0, 0, 0, 0.03);
  height: 6rem;
  display: flex;
  align-items: center;
  gap: 3rem;
}

.navbar {
  display: flex;
  align-items: center;
  height: 100%;
  margin: 0 auto;
  overflow: hidden;
  background-color: #191919;

  &__menu {
    position: relative;
    display: flex;
  }

  &__link {
    position: relative;
    display: flex;
    flex-direction: column;
    gap: 0.6rem;
    align-items: center;
    justify-content: center;
    height: $linkHeight;
    width: $linkWidth;
    color: $text;
    transition: $transition;
    text-decoration: none;
    width: $linkWidth;
    text-transform: uppercase;
    transition: 500ms ease all;

    svg {
      transition: 500ms ease all;
    }

    &:hover {
      svg {
        stroke: $primary;
      }
    }

    .navbar:not(:hover) &:focus,
    &:hover {
      span {
        opacity: 1;
        transform: translate(0);
      }
    }
  }

  &__item {
    &:last-child {
      &:before {
        content: '';
        position: absolute;
        left: -8rem;
        margin-left: $linkWidth/2;
        bottom: -1.25rem;
        height: 0.5rem;
        width: 2px;
        background: $primary;
        $speedlineColor: rgba(#fff, 0.2);
        $speedGap: 3rem;
        $shadow: 0 -0.5rem $primary, 0 -0.5rem $primary, 0 0 $speedGap 0.5rem $primary, 2rem 0 0 $speedlineColor, -$speedGap 0 0 $speedlineColor;
        @for $i from 2 to 120 {
          $shadow: $shadow + #{","}+ $i*$speedGap 0 0 $speedlineColor;
          $shadow: $shadow + #{","}+ $i*-$speedGap 0 0 $speedlineColor;
        }
        box-shadow: $shadow;
        transition: 500ms ease all;
      }
    }

    @for $i from 1 to 12 {
      &:first-child:nth-last-child(#{$i}),
      &:first-child:nth-last-child(#{$i}) ~ li {
        @for $j from 1 to $i {
          &:nth-child(#{$j}):hover, {
            ~ li:last-child:before {
              left: (100% / $i) * ($j - 1);
            }
          }
        }

        &:last-child:hover:before, {
          left: (100% / $i) * ($i - 1);
        }
      }
    }

  }
}
</style>
