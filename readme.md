# Sass Reference

-[how to use extend][extend]

[extend]:#how-to-use-extend
[home]:#sass-reference

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