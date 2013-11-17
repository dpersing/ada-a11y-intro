# Intro to Accessibility

## What Is Web Accessibility?

Web accessibility means making online content usable (and enjoyable!) for people with physical, cognitive, and learning disabilities that affect how they interact with the web.

"Accessibility" is often abbreviated to "a11y."

## Why Be Accessible Online?

* The web is an equalizing force in people's ability to get things done on a daily basis
* Accessible websites typically are search engine-friendly websites
* Accessible websites typically work well on mobile and tablet devices
* It's easier than it sounds!

## Major Use Cases

* **Vision** (blindness, low vision, color blindness)
* **Hearing** (deafness)
* **Motor skills** (inability to use a mouse)
* **Cognitive and learning issues** (autism, dyslexia, ADD, etc.)

## Devices and Supports

* **Screen readers** and braille readers for hearing/reading text, images, controls
* **Screen magnification** for low-vision users
* **Keyboard-only navigation**, or navigation with a joystick or other simplified interface
* **Captions and transcripts** for video and audio

## Standards for Accessibility

W3C's [Web Content Accessibility Guidelines](http://www.w3.org/TR/WCAG20/) provides principles and techniques for making web content:

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

## How to Make Accessible Content

1. Use HTML, CSS, and Javascript correctly.
2. Create good content with logical organization that humans and machines can understand.
3. Supplement valid HTML with some extra attributes that provide more information to screen readers, when appropriate.

That's it!

## How to Test for Accessibility

### Automated Tests

#### HTML and CSS validation

The first step for automated testing is validating your HTML and CSS.

* [Validator.nu (X)HTML5 Validator](http://html5.validator.nu/)

#### WCAG audit

The second step is running an automated test against WCAG 2.0 principles. These tests will sometimes find false positives for issues, but are a great way to get accustomed to WCAG and techniques for fixing a11y issues issues.

### Manual Tests

#### Keyboard-only testing

Test using all of the interactive parts of your page using the keyboard alone.

* **Tab:** Move between interactive elements.
* **Return/Enter:** "Click" on links or buttons.
* **Up and down arrows:** Select a radio button from a set, or an option from a select element.
* **Spacebar:** Select a choice from a radio button set or select element.

[Try out using the keyboard with different interactive elements.](http://dpersing.github.io/ada-a11y-intro/demo/keyboard-test.html)

#### Screen reader testing

Test your page with a screen reader, or a screen reader emulator, to see how a user might actually hear the page.

Today we'll be testing with VoiceOver on your Mac. To use VoiceOver:

1. Open System Preferences > Accessibility.
1. Select "VoiceOver" from the menu.
1. Check the box.

Or, just press Command (&#8984;) + F5 to toggle VoiceOver on or off.

![OSX System Preferences screen, with the Accessibility menu item circled in pink](img/system-a11y-osx.png)

## Some Examples

### HTML for Accessibility

Using valid HTML elements to display text creates a well-structured document and also allows screen reader users to use keyboard shortcuts to "skim" the page by browsing for headers, links, tables, form fields, etc.

#### HTML5 semantic containers

Newer screen readers can pick up on the meaning of semantic HTML5 container elements, creating rich context for reading and browsing.

	* container code sample and demo

#### Semantic text elements

Valid and well-written header elements `<h1>` through `<h6>` create a kind of outline of the page.

Paragraphs (`<p>`), lists (`<ol>` and `<ul>`), and other types of elements create logical reading experiences.

	* semantic code sample and demo

#### Links

Links are read by their text, so make text links clear and unique.

	* link code sample and demo

#### Images

Images should have `alt` attributes that provide a useful description of the image. If the image is for decoration only, it should be applied through CSS, or should have an empty `alt` value.

	* image code sample and demo

Always have a text equivalent for information that is presented in a non-text format.

#### Data tables

Data tables should always have headers (`<th>`) to help situate data.

	* table code sample and demo

#### Form fields

Form fields should always have labels or, in the case of buttons, clear text. Elements presented in sets, like radiobuttons and checkboxes, should be grouped with a `<fieldset>` element.

	* form code sample and demo

### CSS for Accessibility

#### Color contrast for text

For users who can't see well and/or who suffer from color blindness, text and backgrounds need to have sufficient contrast to be visible.

	* color contrast example

#### Visual keyboard focus states

By default, all browsers show keyboard focus on interactive elements with the `outline` CSS property applied to an element's `:focus` pseudo class.

You can replace this default functionality, or also add to it by changing background colors, adding underlines, etc., with CSS.

	* keyboard focus example

## Putting It All Together

Let's run our tests [while we shop for a vacation](http://dpersing.github.io/ada-a11y-intro/demo/index.html).

## More Advanced Stuff

### WAI-ARIA

(WAI-ARIA) is designed to enhance already well-formed HTML for even greater accessibility.

	* ARIA code sample and example

### Screen-Reader-Only Text

Information designed for screen readers specifically can be hidden from sighted users.

	* ARIA code sample and example

Why not just use `display: none;`?

### Accessible Dynamic Content

If a user does something that dynamically loads content on the current page, it's helpful to **change context and move keyboard focus** to that new content so that screen reader and keyboard users can have a smoothly flowing experience.

Javascript can be used in conjunction with WAI-ARIA attributes to create a rich, informative experience for screen reader users by dynamically adding and removing different attributes or attribute values as interactions occur.

## Resources

* [Web Content Accessibility Guidelines (WCAG) 2.0](http://www.w3.org/TR/WCAG20/)
* [Accessibility Developer Tools](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en) extension for Chrome
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
1. Update your HTML with any element or attribute changes or updates.
1. Rerun your tests.
1. Have a partner test your project with VoiceOver.