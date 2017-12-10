# Sass Reference

- [how to use extend][extend]
- [how to use interpolation][interpolation]
- [how to use for loop][for]
- [how to use each directive][each]
- [how to create a list][list]
- [how to use a while loop][while]

[while]:#how-to-use-a-while-loop
[list]:#how-to-create-a-list
[each]:#how-to-use-each-directive
[for]:#how-to-use-for-loop
[interpolation]:#how-to-use-interpolation
[extend]:#how-to-use-extend
[home]:#sass-reference

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