**Mixins for different screens inside CSS-rule**

// Mixin for styles for mobile phone

@mixin only-mobile($property, $value) {
  @media screen and (min-width: $minMobile) and (max-width: calc($minTablet - 1px)) {
    #{$property}: $value;
  }
}

// Mixin for styles for tablet

@mixin only-tablet($property, $value) {
  @media screen and (min-width: $minTablet) and (max-width: calc($minDesktop - 1px)) {
     #{$property}: $value;
  }
}

// Mixin for styles for desktop

@mixin only-desktop($property, $value) {
  @media screen and (min-width: $minDesktop) {
     #{$property}: $value;
  }
}

// Mixin for common styles for mobile phone and tablet

@mixin mobile-and-tablet($property, $value) {
  @media screen and (min-width: $minMobile) and (max-width: calc($minDesktop - 1px)) {
     #{$property}: $value;
  }
}

// Mixin for common styles for tablet and desktop

@mixin tablet-and-desktop($property, $value) {
  @media screen and (min-width: $minTablet) {
     #{$property}: $value;
  }
}

// Mixin for styles for screens less than mobile phone

@mixin less-then-mobile($property, $value) {
  @media screen and (max-width: calc($minMobile - 1px)) {
     #{$property}: $value;
  }
}

**Variables** (should be declared before using mixins):
$minMobile
$minTablet
$minDesktop

_Sample:_

_SASS:_
.page-header {
  padding-top: 10px;
  padding-bottom: 10px;
  border-bottom: 1px solid #E4C7B3;
  background-color: #FAFAFA;

  @include only-tablet(padding-top, 18px);
  @include only-tablet(padding-bottom, 18px);

  @include only-desktop(padding-top, 23px);
  @include only-desktop(padding-bottom, 23px);
}

_CSS:_
.page-header {
  padding-top: 10px;
  padding-bottom: 10px;
  border-bottom: 1px solid #E4C7B3;
  background-color: #FAFAFA;
}
@media screen and (min-width: 768px) and (max-width: 1199px) {
  .page-header {
    padding-top: 18px;
  }
}
@media screen and (min-width: 768px) and (max-width: 1199px) {
  .page-header {
    padding-bottom: 18px;
  }
}
@media screen and (min-width: 1200px) {
  .page-header {
    padding-top: 23px;
  }
}
@media screen and (min-width: 1200px) {
  .page-header {
    padding-bottom: 23px;
  }
}
