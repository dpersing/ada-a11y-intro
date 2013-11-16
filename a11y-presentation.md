# Intro to Accessibility

## What Is Web Accessibility?

Web accessibility means making online content usable (and enjoyable!) for people with physical, cognitive, and learning disabilities that affect how they interact with the web.

## Why Be Accessible?

(Besides being the right thing to do, of course.)

* The population of people using the web is aging
* The web is an equalizing force in people's ability to get things done on a daily basis
* Accessible websites typically are SEO-friendly websites
* Accessible websites typically work well on mobile and tablet devices
* It's easier than it sounds

## Major Use Cases

* **Vision** (blindness, low vision, color blindness)
* **Hearing** (deafness)
* **Motor skills** (inability to use a mouse)
* **Cognitive and learning issues** (autism, dyslexia, ADD, etc.)

## Devices and Supports

* **Screen readers** and braille readers for text and images
* **Screen magnification** for low-vision users
* **Keyboard-only navigation**, or navigation with a joystick or other simplified interface
* **Captions and transcripts** for video and audio

## Standards for Accessibility

W3C's [Web Content Accessibility Guidelines](http://www.w3.org/TR/WCAG20/) provides principles and techniques for making web content:

1. Perceivable
1. Operable
1. Understandable
1. Robust

## In Other Words

Can a user...

1. see or hear content
1. interact with content
1. understand and navigate content
1. use the content on the device of their choice and with the technology of their choice

... in a way that works for them?

## How to Make Accessible Content

1. Use HTML, CSS, and Javascript correctly.
2. Create good content with logical organization that humans and machines can understand.
3. Supplement valid HTML with WAI-ARIA attributes that provide more information to screen readers.

## How to Test for Accessible Content

* Automated tests
	* HTML validation
	* WCAG validation
* Manual tests
	* Keyboard-only interaction
	* Screen reader

## Some Examples

### HTML for Accessibility

#### Headers and Semantics

#### Links

#### Form Fields

### CSS for Accessibility

#### Color Contrast for Text

#### Visual :focus States

### Creating More Structure and Relationships with WAI-ARIA

#### Major ARIA Roles

## Accessible Dynamic Content

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