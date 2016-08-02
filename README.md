### Working With Auto Layout and Layout Anchors

#### Author: Bart Jacobs

Creating layout constraints in code is not pretty. It is not always intuitive and it is verbose, even if you decide to use Apple's [Visual Format Language](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/AutolayoutPG/VisualFormatLanguage.html).

In iOS 9 and OS X El Capitan, Apple introduced the `NSLayoutAnchor` class to make working with layout constraints in code easier and more intuitive. I must admit I was a bit skeptical at first. Even the **Visual Format Language** makes it difficult to manage constraints, how would another API make it easier.

Fortunately, I was wrong. The `NSLayoutAnchor` class makes creating and managing constraints almost painless. In addition to the `NSLayoutAnchor` class, Apple added a number of properties to `UIView` and `NSView`. The result is pretty nice.

## How It Works?

There are a few things you need to know about the `NSLayoutAnchor` class. First, you are not supposed to explicitly create instances of the `NSLayoutAnchor` class. Instead, you obtain a reference to a layout anchor from the `UIView` or `NSView` you are working with. How that works becomes clear in a few minutes.

Second, the `NSLayoutAnchor` class can be considered an abstract class. In practice, you interact with one of its subclasses:

- `NSLayoutDimension`: This subclass is used to create layout constraints that describe the width and height of a view.
- `NSLayoutXAxisAnchor`: This subclass is used to create horizontal layout constraints.
- `NSLayoutYAxisAnchor`: This subclass is used to create vertical layout constraints.

Third, the existing APIs for programmatically creating layout constraints do not warn you if you are defining invalid layout constraints. The `NSLayoutAnchor` class adds type checking to the mix, warning you about potential problems at compile time. While this is not 100% waterproof, it certainly helps creating the right set of constraints and facilitates debugging Auto Layout issues.

**Read this article on the [blog](https://cocoacasts.com/working-with-auto-layout-and-layout-anchors/)**.
