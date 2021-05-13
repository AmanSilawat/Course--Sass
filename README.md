# Course--Sass

Enable a Visual Studio Extension [live sass compiler](https://marketplace.visualstudio.com/items?itemName=ritwickdey.live-sass)

## Auto-Prefix

In the `style.scss`
```css
header {
	display: flex;
	justify-content: center;
	align-item: center;
}
```

Auto generate the `style.css` with `Autoprefixer`
```css
header {
	display: -webkit-box;
	display: -ms-flexbox;
	display: flex;
	-webkit-box-pack: center;
	-ms-flex-pack: center;
	justify-content: center;
	align-item: center;
}
```

## Variables

```css
$primaryBtn: rgb(50, 146, 140);
$secondary: rgb(80, 210, 50);

header button {
	background: $primaryBtn;
}
```

<br />

## Nesting

```css
header {
	background: gray;
	button {
		background: $primaryBtn;
		&:hover {
			background: $secondary;
		}
		&::after {
			content: 'Wow SASS is amazing';
		}
	}
	p {
		color: purple;
	}
	.className {
		font-weight: 600;
	}
}
```

<br />

## Separate files with partials

Create `_header.scss`

```css
header {
	background: gray;
	button {
		background: $primaryBtn;
		&:hover {
			background: $secondary;
		}
		&::after {
			content: 'Wow SASS is amazing';
		}
	}
	p {
		color: purple;
	}
	.className {
		font-weight: 600;
	}
}
```

<br />

Create `_variables.scss`

```css
$primaryBtn: rgb(50, 146, 140);
$secondary: rgb(80, 210, 50);
```

Create `main.scss`

```css
@import './_header';
@import './_variables';

header button {
	background: $primaryBtn;
}
```

<br />

## Functions

```css
@mixin flexCenter {
	display: flex;
	justify-content: center;
	align-item: center;
}
header {
	@include flexCenter();
	background: gray;
}
```

<br />

### Function Parameter

```css
@mixin flexCenter($bgColor) {
	height: 100vh;
	background: $bgColor;
}
header {
	@include flexCenter(red);
}

section {
	@include flexCenter(gray);
}
```

<br />

## Extend

Inherit all the styles from the `header`

```css
.about {
	@extend header;
	color: blue; /* add own style */
}
```

<br />

## Calculation

```css
.about {
	@extend header;
	width: 100% - 25%;
}
```
