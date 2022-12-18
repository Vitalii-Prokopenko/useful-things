**Mixin for font styles**

@mixin fonts($size: false, $weight: false, $lh: false, $my-color: false) {
  @if $size {
    font-size: $size;
  }
  @if $weight {
    font-weight: $weight;
  }
  @if $lh {
    line-height: calc($lh / $size);
  }
  @if $my-color {
    color: $my-color;
  }
}

**Variables** (no need to previously declare)

_Sample:_

_SASS:_

.contact {
  @include fonts(24px, 700, 28px, orange);

  &:hover {
    @include fonts(24px, 700, 28px, yellow);
  }
}

_CSS:_

.contact {
  font-size: 24px;
  font-weight: 700;
  line-height: 1.1666666667;
  color: orange;
}
.contact:hover {
  font-size: 24px;
  font-weight: 700;
  line-height: 1.1666666667;
  color: yellow;
  }