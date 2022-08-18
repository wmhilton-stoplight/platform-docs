---
stoplight-id: 1g5milt5ociq8
---

# Customize Images in Stoplight Flavored Markdown

Stoplight Flavored Markdown has a few additional properties you can use to customize how your images are displayed in your documentation.

**Default**

The default setting adds an outline and "click-to-zoom" for images. 

![Stoplight Logo](https://stoplight.io/images/home/logo-blue-black.png)

```md title="Try it out!"
![Stoplight Logo](https://stoplight.io/images/home/logo-blue-black.png)
```

**Center Focus**

Make screenshots pop out with a center focus and a default background image. 

<!-- focus: center -->

![Docs portal settings](https://i.imgur.com/YCb6MWI.png)

```md title="Try it out!"
<!-- focus: center -->

![Docs portal settings](https://i.imgur.com/YCb6MWI.png)
```

**Add a Caption**

Add an optional caption to further explain the screenshot. 

<!-- focus: top -->

![Studio project share](https://i.imgur.com/ueOOL8X.png 'Can add an optional caption')

```md title="Try it out!"
<!-- focus: top -->

![Studio project share](https://i.imgur.com/ueOOL8X.png 'Can add an optional caption')
```

**Try a Different Background Color**

<!--
focus: top
bg: primary
-->

![Studio project share](https://i.imgur.com/ueOOL8X.png)

```md title="Try it out!"
<!--
focus: top
bg: primary
-->

![Studio project share](https://i.imgur.com/ueOOL8X.png 'Can add an optional caption')
```

**Use a Hex Background Color**

<!--
focus: top
bg: "#f78ae0"
-->

![Studio project share](https://i.imgur.com/ueOOL8X.png)


```md title="Try it out!"
<!--
focus: top
bg: "#f78ae0"
-->

![Studio project share](https://i.imgur.com/ueOOL8X.png)
```

**Good Old Plain Images**

<!-- focus: false -->
![Studio project share](https://i.imgur.com/ueOOL8X.png)


```md title="Try it out!"
<!--
focus: false
-->
```