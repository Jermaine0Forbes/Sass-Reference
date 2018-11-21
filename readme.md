# Sass Reference

- [how to use extend][extend]
- [how to use interpolation][interpolation]
- [how to use for loop][for]
- [how to use each directive][each]
- [how to create a list][list]
- [how to use a while loop][while]
- [how to import other sass files][import]
- [how to use mixins][mixin]
- [how to loop through multiple lists][loop-lists]
- [how to loop through nested lists][nested-lists]

[nested-lists]:#how-to-loop-through-nested-lists
[loop-lists]:#how-to-loop-through-multiple-lists
[mixin]:#how-to-use-mixins
[import]:#how-to-import-other-sass-files
[while]:#how-to-use-a-while-loop
[list]:#how-to-create-a-list
[each]:#how-to-use-each-directive
[for]:#how-to-use-for-loop
[interpolation]:#how-to-use-interpolation
[extend]:#how-to-use-extend
[home]:#sass-reference

### how to loop through nested lists
<details>
  <summary>
  View Content
  </summary>


**CSS**
```css
$list: ("red",#ff4d4d), ("blue",#3366ff),("green",#009933);

/****************
  GENERAL
****************/

@for $i from 1 through length($list){

  $col: nth($list, $i);
  $hover: nth($col,2);
  $bg: nth($col,1);

  a{
    color: $bg;

    &:hover{
      color:$hover;
    }
  }

}
```

**SCSS**
```css

a
{
    color: 'red';
}
a:hover
{
    color: #ff4d4d;
}

a
{
    color: 'blue';
}
a:hover
{
    color: #36f;
}

a
{
    color: 'green';
}
a:hover
{
    color: #093;
}
```


</details>

[go back :house:][home]

### How to loop through multiple lists

**reference**
- [stackoverflow](https://stackoverflow.com/questions/37343932/sass-each-loop-with-multiple-lists)

```css

$ids: 21, 33, 73;
$colors: #fff, #000, #333;

@for $i from 1 through length($ids) {
  $id: nth($ids, $i);
  $color: nth($colors, $i);
    .category--#{$id},
    .post--#{$id} {
       color: #{$color};
    }
}
```

[go back home][home]

### How to use mixins

Mixins are similar to functions you can name the mixin and you can
add parameters to the mixin so that the values in the properties will
change. Not only that, any property that has dashes in them can be broken
up into another bracket. As you will see down below

#### Breaking dashes up into brackets

Instead of adding the properties font-weight, font-size, or font-family.
You can break it up into a bracket as you see here. And if you want
to add the mixin into a class or id you use the keyword `@include`.
```css
@mixin font-styling{
	font:{
		size:2em;
		weight:bold;
		family:helvetica,georgia,sans-serif;
	}
}


	#summary{


	background:teal;
	color:white;

	@include font-styling;

	}
```

#### Adding parameters

Adding parameters allows you the change the values of the properties.
In addition to that, you can set up default values within the parameters

```css
@mixin texting($pad, $color,$size:1.2em){

	font-size:$size;
	padding: $pad;
	background: $color;

	text:{
		transform:uppercase;
		decoration:underline;
	}
}

#summary-2{
		@include texting(1.2em, #e44, 18px);
	}

```



[go back home][home]

### How to import other sass files

```css

@import "header";
```

[go back home][home]

### How to use a while loop

**reference**
- [docs](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#_while)

```css
$i: 6;
@while $i > 0 {
  .item-#{$i} { width: 2em * $i; }
  $i: $i - 2;
}
```

[go back home][home]

### How to create a list

**reference**
- [docs](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#Lists)

```css
$list : (one, two, three);
```

[go back home][home]

### How to use each directive

**reference**
- [docs](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#_each__each-directive)

**syntax**: `@each $var in <list or map>`

```css
$list: (puma, sea-slug, egret, salamander);

@each $animal in $list {
  .#{$animal}-icon {
    background-image: url('/images/#{$animal}.png');
  }
}
```

[go back home][home]

### How to use for loop

**reference**
- [docs](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#_for)

**syntax**: `@for $var from <start> to <end>`

```css
@for $i from 1 through 3 {
  .item-#{$i} { width: 2em * $i; }
}

```


[go back home][home]


### How to use interpolation

You can also use Sass variables in selectors and property names using #{} interpolation syntax

```css
$name: foo;
$attr: border;
p.#{$name} {			// outputs: p.foo
  #{$attr}-color: blue;// outputs: border-color
}


```

[go back home][home]

### How to use extend

The `@extend` key word include a class properties
into another class

```css

.first-class{
	font-size:2em;
	text-decoration:underline;
}

.second-class{

	@extend first-class;
	color:blue;
}

```

[go back home][home]
