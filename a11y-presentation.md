# Intro to Accessibility

## What Is Web Accessibility?

Web accessibility means making online content usable (and enjoyable!) for people with physical, cognitive, and learning disabilities that affect how they interact with the web.

**Fun fact:** "Accessibility" is often abbreviated to "a11y" for hashtaggery.

## Why Be Accessible Online?

* The web is an equalizing force in people's ability to get things done on a daily basis:
	* Paying bills
	* Buying essentials
	* Signing up for services
	* Communicating
* Accessible websites typically are search engine-friendly websites
* Accessible websites typically work well on mobile and tablet devices
* It's easier than it sounds!

## Major Use Cases

* **Vision** (blindness, low vision, color blindness)
	* Over 6,500,000 adults, most of them between 18 and 64, and over 650,000 children in the US reported issues related to low vision or blindness in 2011.
	* About 1 in 10 men are color blind.
* **Hearing** (deafness)
	* About 36 million adults in the US have some form of hearing loss.
	* About 2 in 1000 children in the US are born deaf.
* **Motor skills** (trouble with using a mouse)
* **Cognitive and learning issues** (autism, dyslexia, ADD, etc.)
	* About 1 in 88 children in the US are on the autism spectrum.
	* Probably about 20% of people have some form of dyslexia.
	* 11% of children 4-17 years of age, and about 4% of adults, in the US have been diagnosed with ADD.

References:
* [Statistical Facts about Blindness in the United States (2011)](https://nfb.org/factsaboutblindnessintheus)
* [Color blindness - PubMed Health](http://www.ncbi.nlm.nih.gov/pubmedhealth/PMH0001997/)
* [Quick Statistics - National Institute on Deafness and Other Communication Disorders](http://www.nidcd.nih.gov/health/statistics/Pages/quick.aspx)
* [Autism Spectrum Disorders - CDC](http://www.cdc.gov/ncbddd/autism/data.html)
* [Debunking the Myths about Dyslexia - University of Michigan](http://dyslexiahelp.umich.edu/dyslexics/learn-about-dyslexia/what-is-dyslexia/debunking-common-myths-about-dyslexia)
* [ADHD - CDC](http://www.cdc.gov/ncbddd/adhd/data.html)
* [ADHD in Adults - PubMed](http://www.webmd.com/add-adhd/guide/adhd-adults)

## Devices and Supports

* **Screen readers** and braille readers for hearing/reading text, images, controls
* **Screen magnification** for low-vision users
* **Keyboard-only navigation**, or navigation with a joystick or other simplified interface
* **Captions and transcripts** for video and audio

## Standards for Accessibility

W3C's [Web Content Accessibility Guidelines](http://www.w3.org/TR/WCAG20/) (WCAG) provides principles and techniques for making web content:

1. Perceivable
1. Operable
1. Understandable
1. Robust

In other words, can a user...

1. access content
1. use interactive elements
1. understand and navigate content
1. use the content on the device of their choice and with the technology of their choice

... in a way that works for them?

WCAG is currently in its second version, so it's often called WCAG 2.0. WCAG also has three levels of compliance, from least strict (Level A) to most strict (Level AAA). **Most commonly we target Level AA**.

## How to Make Accessible Content

1. Use HTML, CSS, and Javascript correctly.
1. Create good content with logical organization that humans and machines can understand, including text alternatives for all visual content. (YouTube does captions, for example, and creates them by default!)
1. Supplement valid HTML with some extra attributes that provide more information to screen readers, when appropriate.

That's it!

## How to Test for Accessibility

### Automated Tests

#### HTML validation

The first step for automated testing is validating your HTML.

* [W3C Markup Validation Service](http://validator.w3.org/)
* [Validator.nu (X)HTML5 Validator](http://html5.validator.nu/)

#### WCAG audit

The second step is running an automated test against WCAG 2.0 principles. These tests will sometimes find false positives for issues, but are a great way to get accustomed to WCAG and techniques for identifying and fixing a11y issues.

* [Chrome Accessibility Developer Tools](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en) is an add-on for Chrome that adds an accessibility audit to the existing Web Inspector tools.
* [HTML_Codesniffer](http://squizlabs.github.io/HTML_CodeSniffer/) is an in-browser tool and bookmarklet for any browser that checks your code against WCAG 2.0.

### Manual Tests

#### Keyboard-only testing

Test using all of the interactive parts of your page using the keyboard alone.

* **Tab:** Move between interactive elements.
* **Return/Enter:** "Click" on links or buttons.
* **Up and down arrows:** Select a radio button from a set, or an option from a select element.
* **Spacebar:** Select a choice from a select element, or check a checkbox.

#### Screen reader testing

Test your page with a screen reader, or a screen reader emulator, to see how a user might actually hear the page. **Keep in mind that all screen readers work slightly differently: they have different shortcut keys and may identify (or not identify) information on the page differently.**

Today we'll be testing with VoiceOver, the screenreader that comes free with your Mac. To use VoiceOver:

1. Open System Preferences > Accessibility.
1. Select "VoiceOver" from the menu.
1. Check the box.

Or, just press **Command (&#8984;) + F5** to toggle VoiceOver on or off.

The first time you run VoiceOver you'll be prompted to go through a tutorial. Use the tutorial and the reference links at the bottom to learn VoiceOver's keyboard shortcuts.

![OSX System Preferences screen, with the Accessibility menu item circled in pink](http://dpersing.github.io/ada-a11y-intro/demo/img/system-a11y-osx.png)

## Some Examples

### HTML for Accessibility

Using valid HTML elements to display text creates a well-structured document and also allows screen reader users to use keyboard shortcuts to "skim" the page by browsing for headers, links, tables, form fields, etc.

#### Semantic text elements

Valid and well-written header elements `<h1>` through `<h6>` create a kind of outline of the page.

Paragraphs (`<p>`), lists (`<ol>` and `<ul>`), and other types of elements create logical reading experiences.

```
<h1>Every page should have an h1!</h1>

<h2>Smaller sections should have h2s</h2>

<h3>And then h3s, if appropriate, etc.</h3>

<p>Blocks of text should usually be paragraphs.</p>

<ul>
	<li>Lists should be used for</li>
	<li>Well, lists</li>
	<li>You know</li>
</ul>
```

#### Links

Links are read by their text, so make text links clear and unique.

```
<a href="http://adadevelopersacademy.org/">This link</a>
```

and

```
<a href="https://twitter.com/adaacademy">this link</a>
```

will usually read the same to screen readers, even though they go to different URLs.

#### Images and other media

Images should have `alt` attributes that provide a useful description of the image. If the image is for decoration only, it should be applied through CSS, or should have an empty `alt` value.

```
<img src="http://placekitten.com/300/300" alt="an adorable tabby kitten">
```

Always have a text equivalent for information that is presented in a non-text format, such as images, standalone icons, videos, etc.

#### Data tables

Data tables should always have headers (`<th>`) to help situate data, and `scope` attributes for multiple headers on different axes.

```
<table>
	<caption>Upcoming Birthdays</caption>
	<tr>
		<th scope="col">Name</th>
		<th scope="col">Date</th>
	</tr>
	<tr>
	<th scope="row">Laura</th>
		<td>December 6</td>
	</tr>
	<tr>
		<th scope="row">Bill</th>
		<td>December 12</td>
	</tr>
	<tr>
		<th scope="row">Kai</th>
		<td>December 14</td>
	</tr>
	<tr>
		<th scope="row">Jessica</th>
		<td>January 8</td>
	</tr>
	<tr>
		<th scope="row">Kayle</th>
		<td>January 9</td>
	</tr>
</table>
```

#### Form fields

Form fields should always have labels or, in the case of buttons, clear text. Elements presented in sets, like radiobuttons and checkboxes, should be grouped with a `<fieldset>` element.

```
<form>
	<label>Name
		<input type="text">
	</label>
	<label>Phone
		<input type="text">
	</label>
	<fieldset>
		<legend>Order type</legend>
		<label>Takeout
			<input type="radio" name="order" value="takeout">
		</label>
		<label>Delivery
			<input type="radio" name="order" value="delivery">
		</label>
	</fieldset>
	<fieldset>
		<legend>Toppings</legend>
		<label>Extra cheese
			<input type="checkbox" name="toppings" value="cheese">
		</label>		
		<label>Mushrooms
			<input type="checkbox" name="toppings" value="mushrooms">
		</label>
		<label>Pepperoni
			<input type="checkbox" name="toppings" value="pepperoni">
		</label>
		<label>Pineapple
			<input type="checkbox" name="toppings" value="pineapple">
		</label>
	</fieldset>
	<button type="submit">Submit order</button>
</form>
```

There are also a couple of ways to tie labels to fields:

* Nest the field inside the label like above
* Use attributes to tie the label to the field like this:

```
<label for="phone">Phone</label>
<input type="text" id="phone">
```

### CSS for Accessibility

#### Color contrast for text

For users who can't see well and/or who suffer from color blindness, text and backgrounds need to have sufficient contrast to be visible.

[Let's look at some examples.](http://dpersing.github.io/ada-a11y-intro/demo/color-contrast.html)

#### Visual keyboard focus states

By default, all browsers show keyboard focus on interactive elements with the `outline` CSS property applied to an element's `:focus` pseudo class.

You can replace this default functionality, or also add to it by changing background colors, adding underlines, etc., with CSS.

#### Screen-reader-only CSS

Sometimes you'll want to add extra text for screen readers. This might be because information is conveyed visually with icons, or colors, or other design elements.

This can be done with some CSS that we can apply with a class on any element:

```
.visuallyhidden { 
  position: absolute; 
  overflow: hidden; 
  clip: rect(0 0 0 0); 
  height: 1px; width: 1px; 
  margin: -1px; padding: 0; border: 0; 
}
```

### WAI-ARIA

[Web Accessibility Initiative Accessible Rich Internet Applications](http://www.w3.org/TR/wai-aria/) (WAI-ARIA) are designed to enhance already well-formed HTML for even greater accessibility.

WAI-ARIA consists of different types of attributes used to convey more information about elements and relationships between elements to screen readers. Newer screen readers can identify these values and use them when they're announcing content to users.

Here are some examples!

* `role` indicates the element's role on the page. In this case, we have a navigation group, which most newer screen readers will be able to identify.
* `aria-labelledby` will help tie a clear relationship between things that are in groups or hierarchies.

```
<nav role="navigation">
	<ul>
		<li><a href="#" id="nav-tops">Tops</a>
			<ul aria-labelledby="nav-tops">
				<li><a href="tops/t-shirts.html">T-Shirts</a></li>
				<li><a href="tops/tanks.html">Tanks</a></li>
				<li><a href="tops/button-ups.html">Button-Ups</a></li>
			</ul>
		</li>
		<li><a href="#" id="nav-bottoms">Bottoms</a>
			<ul aria-labelledby="nav-bottoms">
				<li><a href="bottoms/jeans.html">Jeans</a></li>
				<li><a href="bottoms/skirts.html">Skirts</a></li>
				<li><a href="bottoms/shorts.html">Shorts</a></li>
			</ul>
		</li>
	</ul>
</nav>

```

There's are whole sets of `role` attributes called Landmark Roles and Document Structure Roles that can be applied to different areas of the page. These form a kind of outline of the types of content that appear on the page and help screen reader users "skim" the page.

```
<header>
	<img src="site-logo.png" role="banner" alt="Site Name">
	<!-- The banner role correlates to a site's logo or name. -->
	<nav role="navigation">
		<!-- Here's where the site global nav might live. -->
	</nav>
	<form role="search">
		<!-- Here's where the site search might live. -->
	</form>
</header>>
<main role="main">
	<!-- The main content of the page would be the main column of text, for example. --> 
</main>
<aside role="complementary">
	<!-- Here's supportive information, like "about" blurbs, or other products, etc. -->
</aside>
<footer role="contentinfo">
	<!-- Meta-information that describes the content, like copyright dates, might live here. -->
</footer>
```

**Fun fact:** If you're noticing similarities between WAI-ARIA roles and HTML5 container elements, that's no accident. WAI-ARIA precedes HTML5, but has similar goals for creating semantic containers and labels for content.

## Putting It All Together

Good news, everyone! We're going on vacation. [Let's run our tests while we learn about the trip!](http://dpersing.github.io/ada-a11y-intro/demo/vacation.html)

## More Advanced Stuff

### WAI-ARIA Widget Roles

What if you want more options for controls and dynamic content on the page? WAI-ARIA Widget Roles provide some enhancements like:

* `alert` roles for important content that should get announced ASAP.
* `progressbar` roles for showing progress load.
* `tab` roles can be easily styled like links or buttons but function like radio buttons.
* `tooltip` roles can provide extra info when a user hovers or clicks on a link or button.

### Combining WAI-ARIA Roles and Javascript

If a user does something that dynamically loads content on the current page, it's helpful to **change context and move keyboard focus** to that new content so that screen reader and keyboard users can have a smoothly flowing experience.

Javascript can be used in conjunction with WAI-ARIA attributes to create a rich, informative experience for screen reader users by dynamically adding and removing different attributes or attribute values as interactions occur and new content loads on the page.

## Resources

### Guidelines and Specs

* [WAI-ARIA](http://www.w3.org/TR/wai-aria/)
* [Web Content Accessibility Guidelines (WCAG) 2.0](http://www.w3.org/TR/WCAG20/)

### Techniques

* [WebAIM](http://webaim.org/) has how-tos, news, and lots of resources related to a11y
* [Web Axe](http://www.webaxe.org/) is a blog and podcast about accessiblity issues
* [Places It's Tempting to Use Display: None; But Don't](http://css-tricks.com/places-its-tempting-to-use-display-none-but-dont/) gives a nice rundown of using CSS to hide content visually-only.

### Tools

* [Accessibility Developer Tools](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en) extension for Chrome
* [HTML_Codesniffer](http://squizlabs.github.io/HTML_CodeSniffer/) browser bookmarklet and in-browser audit tool
* Lou Verou's [Contrast Ratio](http://leaverou.github.io/contrast-ratio/) tool
* [VoiceOver on OSX Commands and Gestures](http://www.apple.com/voiceover/info/guide/_1131.html)
* [VoiceOver on iOS Gestures](http://lab.dotjay.co.uk/notes/voiceover-ios/learning-ios-voiceover-gestures/)
* [Fangs Screen Reader Emulator](https://addons.mozilla.org/en-us/firefox/addon/fangs-screen-reader-emulator/) for Firefox
* [NVDA](http://www.nvaccess.org/), a free screen reader for Windows
* [JAWS](http://www.freedomscientific.com/products/fs/jaws-product-page.asp), a screen reader for Windows with a free demo version
* [ZoomText](http://www.aisquared.com/zoomtext), a screen reader and magnifier for Windows with a free demo version

## Exercises

1. Test your current Sinatra projects for accessibility using VoiceOver and Chrome Accessibility Developer Tools. If it helps, close your eyes! (Also potentially be kind to your neighbors by wearing headphones.)
1. Update your CSS with any color contrast changes. You can use the Contrast Ratio tool to try out different contrasts.
1. Update your HTML with WAI-ARIA Landmark Roles when they are applicable.
1. Update any other HTML elements or attributes that aren't valid or don't read as you expect them to.
1. Rerun your tests.
1. Have a partner test your project with VoiceOver.
