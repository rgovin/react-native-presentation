## WHAT IS REACT NATIVE?
React Native is a JavaScript framework for writing real, natively rendering mobile applications for iOS and Android. Created by Facebook. Firstly release iOS version on March 2015 and Android version on September 2015.
It’s based on React – the Facebook’s JavaScript library for building user interfaces, but instead of targeting the browser, it targets mobile platforms.

The core React Native project supports writing mobile applications for both iOS and Android. Community implementations also provide support for Windows, Ubuntu, the web, and more.

Similar to React for the web, React Native applications are written with a mixture of JavaScript and XML-esque markup, known as JSX. Then, under the hood, the React Native “bridge” invokes the native rendering APIs in Objective-C (for iOS) or Java (for Android). Thus, your application will render using real mobile UI components, not webviews, and will look and feel like any other mobile application. React Native also exposes JavaScript interfaces for platform APIs, so your React Native apps can access platform features like the phone camera or the user’s location.

## WHAT IS REACT?

React is a declarative, efficient, and flexible JavaScript library for building user interfaces. It lets compose complex UIs from small and isolated pieces of code called “components”. It was originally designed to build applications and solve problems on the web. This framework has become extremely popular since its release, with many established companies taking advantage of its quick rendering, maintainability, and declarative UI, among other things. 
React treats everything as a Component – this are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and returns HTML via a render function.

## HOW DOES REACT NATIVE WORK?
In order to understand the technical underpinnings of React Native, we first need to recall one of React’s concepts: the Virtual DOM.

Traditional DOM manipulation is slow and expensive in terms of performance and should be minimized. React bypasses the traditional DOM with something called the virtual DOM: basically, a copy of the actual DOM in memory that only changes when comparing new versions of the virtual DOM to old versions of the virtual DOM. This minimizes the number of DOM operations required to achieve the new state.

In the context of React on the web, most developers think of the Virtual DOM as a performance optimization. The Virtual DOM certainly has performance benefits, but its real potential lies in the power of its abstraction. Placing a clean abstraction layer between the developer’s code and the actual rendering opens up a lot of interesting possibilities. But React could render to a target other than the browser’s DOM. 

Instead of rendering to the browser’s DOM, React Native invokes Objective-C APIs to render to iOS components, or Java APIs to render to Android components. This sets React Native apart from other cross-platform app development options, which often end up rendering web-based views.

This is all possible because of the bridge, which provides React with an interface into the host platform’s native UI elements. React components return markup from their render function, which describes how they should look. With React for the web, this translates directly to the browser’s DOM. For React Native, this markup is translated to suit the host platform, so a `<View>` might become an iOS-specific UIView.

The core React Native project supports iOS and Android. Because of the abstraction layer provided by the Virtual DOM, React Native can target other platforms, too — someone just needs to write the bridge. For example, there are community implementations of React Native for Windows and Ubuntu, so you can also use React Native to create desktop applications.

### RENDERING LIFECYCLE

React takes the idea of diffing and applies it to native components. It takes your UI and sends the smallest amount of data to the main thread to render it with native components. The UI is declaratively rendered based on the state, and React uses diffing to send the necessary changes over the bridge.

When React runs in the browser, the render lifecycle begins by mounting your React component. After that, React handles the rendering and rerendering of your component as necessary. For the render stage, the developer returns HTML markup from a React component’s “render” method, which React then renders directly into the page as necessary.

For React Native, the lifecycle is the same, but the rendering process is slightly different because React Native depends on the bridge. The bridge translates JavaScript calls and invokes the host platform’s underlying APIs and UI elements (i.e., in Objective-C or Java, as appropriate). Because React Native doesn’t run on the main UI thread, it can perform these asynchronous calls without impacting the user’s experience. 
Good benefits of JavaScript is their asynchronous natures. React Native is running on separated thread using JavaScript asynchronous call via the event bridge to invokes the host native platform’s underlying APIs and UI elements. (Objective-C, Java). Since, React Native don’t run on the main UI rendering thread, it can do asynchronous call without impact user’s experience (such as delay).

### HOW DOES REACT NATIVE DRAW?
The core of React Native is the concept of components.

When writing in React for the web, you render normal HTML elements (`<div>`, `<p>`, `<span>`, `<a>`, etc.). With React Native, all of these elements are replaced by platform-specific React components. The most basic is the cross-platform `<View>`, a simple and flexible UI element that can be thought of as analogous to the `<div>`. On iOS, for instance, the `<View>` component renders to a UIView, whereas on Android it renders to a View.

Other components are platform-specific. For instance, the `<DatePickerIOS>` component (predictably) renders the iOS standard date picker. Here is an excerpt, demonstrating an iOS date picker. The usage is straightforward, as you would expect

Because all of our UI elements are now React components rather than basic HTML elements like the `<div>`, you will need to explicitly import each component you want to use. 

Platform-specific components and APIs have special tags in the documentation, and typically use the platform name as a suffix —for example, `<TabBarIOS>` and `<ToolbarAndroid>`.
COMPONENTS EXAMPLES

The framework offers native components out of the box, such as View, Text, and Image, among others. You can create components using these Native components as building blocks. For example, you can use the following markup to create a ViewBoxesWithColorAndText component using React Native View and Text components.

### JSX

In React Native, just as in React, we write our views using JSX, combining markup and the JavaScript that controls it into a single file. JSX met with strong reactions when React first debuted. For many web developers, the separation of files based on technologies is a given: you keep your CSS, HTML, and JavaScript files separate. The idea of combining markup, control logic, and even styling into one language can be confusing.
JSX prioritizes the separation of concerns over the separation of technologies. In React Native, this is even more strictly enforced. In a world without the browser, it makes even more sense to unify our styles, markup, and behavior in a single file for each component. Accordingly, your .js files in React Native are in fact JSX files. If you’ve been using vanilla JavaScript when working with React for the web, you will want to transition to JSX syntax for your work in React Native.


### STYLING NATIVE COMPONENTS

Styled Components is a CSS-in-JS library that enables developers to write each component with their own styles and allows the code to be in a single location. By coupling your styles with the components, it results in optimizing developer experience and output.
In React Native, the styling of components is already done by creating JavaScript objects and if you do not encapsulate them, in most cases, your components and their styling are going to end up in one place.
React Native tends to follow a certain convention when it comes to styling your app. Such as all CSS property names should be in camelCase 
Occasionally, web developers get uncomfortable by these conventions. Using a third party library like styled components can expand opportunities.
You do not have to switch between the context of conventions much, apart from the properties and React Native’s own Flexbox rules.
A component can specify the layout of its children using the Flexbox algorithm called “Flexbox Layout Model”. Flexbox is designed to provide a consistent layout on different screen sizes.
Behind the scenes, styled components just converts the CSS text into a React Native stylesheet object

## CONCLUSION

The main principle of React Native: “Learn once, write everywhere”;

What they meant is that a developer that knows how to write code in React.js will have no problems writing in React native, but not use the same code. React native is built to give the developer the same experience as for web application, no compilation step and the changes appears instantly. What stands out with React Native is that most of the other mobile application frameworks uses programming languages like Objective-C, Java and so on
