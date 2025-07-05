# Crocodil: Concurrency-Safe Dependency Injection for Swift 🐊

![Crocodil Logo](https://example.com/logo.png)

[![Latest Release](https://img.shields.io/github/v/release/unismx/Crocodil)](https://github.com/unismx/Crocodil/releases)
[![License](https://img.shields.io/github/license/unismx/Crocodil)](https://github.com/unismx/Crocodil/blob/main/LICENSE)

## Overview

Crocodil is a concurrency-safe, macro-powered dependency injection framework designed for Swift. It simplifies the management of dependencies in your applications, allowing you to focus on building robust and scalable software. 

## Features

- **Concurrency-Safe**: Built to handle multiple threads without issues.
- **Macro-Powered**: Leverages Swift's macro capabilities for cleaner and more efficient code.
- **Easy to Use**: Simple API that integrates smoothly with existing Swift projects.
- **Flexible**: Supports various dependency injection patterns.

## Installation

To get started with Crocodil, you can add it to your project using Swift Package Manager. Here’s how:

1. Open your Xcode project.
2. Navigate to `File` > `Swift Packages` > `Add Package Dependency`.
3. Enter the repository URL: `https://github.com/unismx/Crocodil.git`.
4. Choose the version you want to use and click `Next`.

## Getting Started

Here’s a quick example of how to use Crocodil in your Swift application.

### Define Your Dependencies

```swift
import Crocodil

protocol Service {
    func doSomething()
}

class MyService: Service {
    func doSomething() {
        print("Doing something!")
    }
}
```

### Register Your Dependencies

```swift
let container = DIContainer()
container.register(Service.self) { _ in MyService() }
```

### Resolve Dependencies

```swift
let service = container.resolve(Service.self)
service.doSomething()
```

## Usage

Crocodil makes it easy to manage dependencies in your applications. Here are some common use cases:

### Singleton Pattern

To create a singleton instance, you can use the following code:

```swift
container.register(Service.self) { _ in MyService() }
    .scope(.singleton)
```

### Scoped Instances

If you need instances that are created for a specific scope, use:

```swift
container.register(Service.self) { _ in MyService() }
    .scope(.session)
```

## Concurrency Support

Crocodil is designed to work seamlessly with Swift's concurrency model. You can safely resolve dependencies in async contexts without worrying about race conditions.

```swift
async {
    let service = await container.resolve(Service.self)
    service.doSomething()
}
```

## Macros in Action

With the power of Swift macros, you can simplify your dependency declarations. Here’s an example:

```swift
@DI
struct MyStruct {
    let service: Service
}
```

This will automatically inject the required dependencies.

## Documentation

For more detailed information on using Crocodil, check out the [documentation](https://github.com/unismx/Crocodil/wiki).

## Examples

Explore the `Examples` folder in the repository for practical implementations of Crocodil in various scenarios.

## Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository.
2. Create a new branch.
3. Make your changes.
4. Submit a pull request.

## License

Crocodil is licensed under the MIT License. See the [LICENSE](https://github.com/unismx/Crocodil/blob/main/LICENSE) file for details.

## Releases

For the latest updates and releases, visit our [Releases](https://github.com/unismx/Crocodil/releases) section. You can download the latest version and execute it in your projects.

## Support

If you have any questions or need help, feel free to open an issue in the repository. 

## Acknowledgments

- Thanks to the Swift community for their ongoing support.
- Special thanks to the contributors who make this project possible.

## Stay Updated

Follow us on GitHub to stay updated with the latest changes and features. 

For any updates or releases, check the [Releases](https://github.com/unismx/Crocodil/releases) section. 

![Crocodil Banner](https://example.com/banner.png)

## Additional Resources

- [Swift Documentation](https://swift.org/documentation/)
- [Dependency Injection in Swift](https://www.example.com/dependency-injection-swift)
- [Concurrency in Swift](https://www.example.com/concurrency-swift)

## Community

Join our community on Discord or Slack to discuss Crocodil and share your experiences. 

## Roadmap

- More examples and documentation.
- Support for more advanced dependency injection patterns.
- Performance optimizations.

## FAQs

**Q: What is dependency injection?**  
A: Dependency injection is a design pattern that allows you to inject dependencies into a class, rather than hard-coding them.

**Q: Why use Crocodil?**  
A: Crocodil provides a clean, efficient way to manage dependencies, especially in concurrent applications.

**Q: Can I use Crocodil with other frameworks?**  
A: Yes, Crocodil can be integrated with various Swift frameworks and libraries.

## Contact

For inquiries, please reach out via the issues section on GitHub or through our community channels.

## Final Note

We appreciate your interest in Crocodil. We believe it can help streamline your development process and enhance your applications. 

For the latest releases, don’t forget to check the [Releases](https://github.com/unismx/Crocodil/releases) section.