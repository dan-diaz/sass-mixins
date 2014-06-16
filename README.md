## media-query
@mixin media-query($size) {
	@if $size == xsmall {
		@media (max-width: 767px) { @content; }
	}
	@else if $size == small {
		@media (min-width: 768px) { @content; }
	}
	@else if $size == medium {
		@media (min-width: 992px) { @content; }
	}
	@else if $size == large {
		@media (min-width: 1200px) { @content; }
	}
}

## font-size
@mixin font-size($sizeValue) {
	font-size: $sizeValue + px;
	font-size: ($sizeValue / 10) + rem;
}

## aspect ratio
@mixin aspect-ratio($width,$height) {
	position:relative;
	width:100%;

	&:before {
		content:'';
		display:block;
		float:left;
		height:100%;
		padding-top:$height/$width * 100%;
	}
}

## simple transition
@mixin transition($seconds) {
	-webkit-transition: all $seconds ease-in;
	-moz-transition: all $seconds ease-in;
	-ms-transition: all $seconds ease-in;
	-o-transition: all $seconds ease-in;
	transition: all $seconds ease-in;
}

## transition with argument for easing
@mixin transition($seconds, $ease) {
	-webkit-transition: all $seconds $ease;
	-moz-transition: all $seconds $ease;
	-ms-transition: all $seconds $ease;
	-o-transition: all $seconds $ease;
	transition: all $seconds $ease;
}

## simple transform
@mixin transform($prop) {
	-webkit-transform: $prop;
	-moz-transform: $prop;
	-ms-transform: $prop;
	-o-transform: $prop;
	transform: $prop;
}

## color lighten
@mixin lighten($color, $multiplier) {
	background-color:adjust-color($color,$lightness:$multiplier);
}