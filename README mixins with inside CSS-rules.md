**Mixins for different screens with inside CSS-rules**

// Mixin for styles for mobile phone

@mixin only-mobile {
  @media screen and (min-width: $minMobile) and (max-width: calc($minTablet - 1px)) {
    @content;
  }
}

// Mixin for styles for tablet

@mixin only-tablet {
  @media screen and (min-width: $minTablet) and (max-width: calc($minDesktop - 1px)) {
     @content;
  }
}

// Mixin for styles for desktop

@mixin only-desktop {
  @media screen and (min-width: $minDesktop) {
     @content;
  }
}

// Mixin for common styles for mobile phone and tablet

@mixin mobile-and-tablet {
  @media screen and (min-width: $minMobile) and (max-width: calc($minDesktop - 1px)) {
     @content;
  }
}

// Mixin for common styles for tablet and desktop

@mixin tablet-and-desktop {
  @media screen and (min-width: $minTablet) {
     @content;
  }
}

// Mixin for styles for screens less than mobile phone

@mixin less-then-mobile {
  @media screen and (max-width: calc($minMobile - 1px)) {
     @content;
  }
}

**Variables** (should be declared before using mixins):
$minMobile
$minTablet
$minDesktop

_Sample:_

_SASS:_

@include tablet-and-desktop {
  .menu
   {
    color: tomato;
    font-size: 23px;

    &:hover {
      color: green;
    }
  }
}

_CSS:_

@media screen and (min-width: 768px) {
  .menu {
    color: tomato;
    font-size: 23px;
  }
  .menu:hover {
    color: green;
  }
}


