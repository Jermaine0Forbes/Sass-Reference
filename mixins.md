# Mixins



### change-color
<details>
  <summary>
  View Content
  </summary>

```css

//  VARIABLE
$l-blue: #42baff;
$blue: #1b98e0;
$d-blue: #004e7a;
$grey: #777777;
$d-grey:#333;
$l-grey:#999;
$l-grey2:#e5e5e5;

$colors: (white,white), (blue,$blue),(grey,$grey),(l-blue,$l-blue),(d-blue,$d-blue),(d-grey,$d-grey),
(l-grey,$l-grey),(l-grey2,$l-grey2);


@mixin change-color($type:"color"){

  @for $i from 1 through length($colors){

  $color: nth($colors,$i);
  $name: nth($color,1);
  $value: nth($color,2);
    &#{$name}{
      #{$type}:$value;
    }
  }

}

/****************
  COLOR
************COL****/

.color-{
@include change-color;
}


.bg-{
  @include change-color("background-color");
}

```

**outputs**
```css
/****************
  COLOR
****************/
.color-white
{
    color: white;
}

.color-blue
{
    color: #1b98e0;
}

.color-grey
{
    color: #777;
}

.color-l-blue
{
    color: #42baff;
}

.color-d-blue
{
    color: #004e7a;
}

.color-d-grey
{
    color: #333;
}

.color-l-grey
{
    color: #999;
}

.color-l-grey2
{
    color: #e5e5e5;
}

.bg-white
{
    background-color: white;
}

.bg-blue
{
    background-color: #1b98e0;
}

.bg-grey
{
    background-color: #777;
}

.bg-l-blue
{
    background-color: #42baff;
}

.bg-d-blue
{
    background-color: #004e7a;
}

.bg-d-grey
{
    background-color: #333;
}

.bg-l-grey
{
    background-color: #999;
}

.bg-l-grey2
{
    background-color: #e5e5e5;
}


```

</details>

[go back :house:][home]
