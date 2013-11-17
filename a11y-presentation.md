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

In othe words, can a user...

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

#### WCAG audit

The second step is running an automated test against WCAG 2.0 principles. These tests will sometimes find false positives for issues, but are a great way to get accustomed to WCAG and techniques for fixing a11y issues issues.

### Manual Tests

#### Keyboard-only testing

Test using all of the interactive parts of your page using the keyboard alone.

#### Screen reader testing

Test your page with a screen reader, or a screen reader emulator, to see how a user might actually hear the page.

Today we'll be testing with VoiceOver on your Mac.

1. Open System Preferences > Accessibility.
1. Select "VoiceOver" from the menu.
1. Check the box.

Or, just press Command + F5 to toggle VoiceOver on or off.

![OSX System Preferences screen, with the Accessibility menu item circled in pink](img/system-a11y-osx.png)

## Some Examples

### HTML for Accessibility

Using valid HTML elements to display text creates a well-structured document and also allows screen reader users to use keyboard shortcuts to "skim" the page by browsing for headers, links, tables, form fields, etc.

#### HTML5 semantic containers

Newer screen readers can pick up on the meaning of semantic HTML5 container elements, creating rich context for reading and browsing.

#### Semantic text elements

Valid and well-written header elements `<h1>` through `<h6>` create a kind of outline of the page.

Paragraphs (`<p>`), lists (`<ol>` and `<ul>`), and other types of elements create logical reading experiences.

#### Links

Links are read by their text, so make text links clear and unique.

#### Images and icons

Images should have `alt` attributes that provide a useful description of the image. If the image is for decoration only, it should be applied through CSS, or should have an empty `alt` value.

Always have a text equivalent for information that is presented in a non-text format.

#### Data tables

Data tables should always have headers (`<th>`) to help situate data.

#### Form fields

Form fields should always have labels or, in the case of buttons, clear text. Elements presented in sets, like radiobuttons and checkboxes, should be grouped with a `<fieldset>` element.

### CSS for Accessibility

#### Color contrast for text

For users who can't see well and/or who suffer from color blindness, text and backgrounds need to have sufficient contrast to be visible.

#### Visual keyboard focus states

By default, all browsers show keyboard focus on interactive elements with the `outline` CSS property applied to an element's `:focus` pseudo class.

You can replace this default functionality, or also add to it by changing background colors, adding underlines, etc., with CSS.

### More Advanced Stuff

#### WAI-ARIA

(WAI-ARIA) is designed to enhance already well-formed HTML for even greater accessibility.

#### Screen-reader-only text

Information designed for screen readers specifically can be hidden from sighted users.

Why not just use `display: none;`?

#### Accessible dynamic content

## Resources

* [Web Content Accessibility Guidelines (WCAG) 2.0](http://www.w3.org/TR/WCAG20/)
* [Accessibility Developer Tools](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en) extension for Chrome
* Lou Verou's [Contrast Ratio](http://leaverou.github.io/contrast-ratio/) tool
* [VoiceOver on OSX Commands and Gestures](http://www.apple.com/voiceover/info/guide/_1131.html)
* [VoiceOver on iOS Gestures](http://lab.dotjay.co.uk/notes/voiceover-ios/learning-ios-voiceover-gestures/)

## Exercises

1. Test your current Sinatra projects for accessibility using VoiceOver and Chrome Accessibility Developer Tools. If it helps, close your eyes!
1. Update your CSS with any color contrast changes. You can use the Contrast Ratio tool to try out different contrasts.
1. Update your HTML with any element or attribute changes or updates.
1. Rerun your tests.
1. Have a partner test your project with VoiceOver.