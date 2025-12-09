# Contributing to AB Repair Manager

Thank you for your interest in contributing to the AB Repair Manager project! This document provides guidelines and instructions for contributing to our repository.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Development Setup](#development-setup)
- [How to Contribute](#how-to-contribute)
- [Issue Reporting Guidelines](#issue-reporting-guidelines)
- [Pull Request Process](#pull-request-process)
- [C# Code Style Standards](#c-code-style-standards)
- [Commit Message Guidelines](#commit-message-guidelines)

## Code of Conduct

We are committed to providing a welcoming and inspiring community for all. Please read and adhere to our Code of Conduct:

- Be respectful and inclusive
- Provide constructive feedback
- Focus on what is best for the community
- Show empathy towards other community members

## Development Setup

### Prerequisites

- **Microsoft Visual Studio 2022** (or later) or **Visual Studio Code** with C# extensions
- **.NET 6.0 SDK** (or the target framework version specified in the project)
- **Git** for version control
- A code editor of your choice

### Setup Steps

1. **Fork the Repository**
   ```bash
   # Navigate to the repository and click the "Fork" button on GitHub
   ```

2. **Clone Your Fork**
   ```bash
   git clone https://github.com/YOUR_USERNAME/ab-repair-manager.git
   cd ab-repair-manager
   ```

3. **Add Upstream Remote**
   ```bash
   git remote add upstream https://github.com/AB-Repair-Manager/ab-repair-manager.git
   ```

4. **Restore Dependencies**
   ```bash
   dotnet restore
   ```

5. **Build the Project**
   ```bash
   dotnet build
   ```

6. **Run Tests**
   ```bash
   dotnet test
   ```

7. **Configure Your IDE**
   - Import the `.editorconfig` file for consistent formatting
   - Install recommended extensions for C# development
   - Configure code formatter to follow the style guidelines below

## How to Contribute

### Types of Contributions

We welcome various types of contributions:

- **Bug Fixes**: Help us identify and fix issues
- **Features**: Implement new functionality
- **Documentation**: Improve or add documentation
- **Tests**: Write unit and integration tests
- **Performance**: Improve code performance and optimization
- **Code Refactoring**: Help improve code quality and maintainability

### Getting Started

1. Create a new branch from `develop` or `main`:
   ```bash
   git checkout -b feature/your-feature-name
   # or for bug fixes
   git checkout -b bugfix/your-bug-name
   ```

2. Make your changes following the code style standards below

3. Write or update tests for your changes

4. Ensure all tests pass:
   ```bash
   dotnet test
   ```

5. Commit your changes with clear messages

6. Push to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```

7. Create a Pull Request

## Issue Reporting Guidelines

### Before Reporting

- Search existing issues to avoid duplicates
- Check the documentation and FAQ
- Verify the issue is reproducible

### Creating an Issue

Please provide the following information when reporting issues:

```markdown
## Description
Clear and concise description of the issue

## Steps to Reproduce
1. Step one
2. Step two
3. ...

## Expected Behavior
What you expected to happen

## Actual Behavior
What actually happened

## Environment
- OS: [e.g., Windows 10, Ubuntu 20.04]
- .NET Version: [e.g., 6.0]
- Visual Studio/Code Version: [if applicable]
- Application Version: [if applicable]

## Screenshots
[If applicable]

## Additional Context
[Any other relevant information]
```

### Issue Labels

- `bug`: Something isn't working
- `enhancement`: New feature or request
- `documentation`: Improvements or additions to documentation
- `good first issue`: Good for newcomers
- `help wanted`: Extra attention is needed
- `question`: Further information is requested
- `wontfix`: This will not be worked on

## Pull Request Process

### Before Creating a PR

1. Ensure your branch is up to date with the base branch:
   ```bash
   git fetch upstream
   git rebase upstream/develop  # or upstream/main
   ```

2. Run all tests locally and ensure they pass

3. Build the project and check for any warnings

### Creating a Pull Request

Use the following template when creating your PR:

```markdown
## Description
Brief description of the changes

## Type of Change
- [ ] Bug fix (non-breaking change that fixes an issue)
- [ ] New feature (non-breaking change that adds functionality)
- [ ] Breaking change (change that causes existing functionality to break)
- [ ] Documentation update

## Related Issues
Closes #[issue number]

## Changes Made
- Change 1
- Change 2
- Change 3

## Testing
Describe the tests you've run to verify your changes:
- [ ] Unit tests
- [ ] Integration tests
- [ ] Manual testing

## Checklist
- [ ] My code follows the code style guidelines
- [ ] I have performed a self-review of my own code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] New and existing unit tests passed locally with my changes
- [ ] Any dependent changes have been merged and published
```

### PR Review Process

1. At least one code review is required before merging
2. Address all review comments
3. Ensure CI/CD pipeline passes
4. Once approved, the PR can be merged

### After Merge

- The branch will be deleted automatically
- Your contribution will be included in the next release notes

## C# Code Style Standards

### General Principles

- Follow Microsoft's [C# Coding Conventions](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)
- Use meaningful and descriptive names for variables, methods, and classes
- Keep methods focused and single-responsibility
- Write self-documenting code with clear intent

### Naming Conventions

```csharp
// Classes, interfaces, and enums: PascalCase
public class UserManager { }
public interface IRepository { }
public enum UserRole { Admin, User }

// Methods: PascalCase
public void CalculateTotal() { }
public string GetUserName() { }

// Properties: PascalCase
public string FirstName { get; set; }
public int Count { get; set; }

// Private fields: camelCase with underscore prefix
private string _userName;
private int _itemCount;

// Local variables: camelCase
int totalAmount = 0;
string firstName = "John";

// Constants: PascalCase
public const int MaxRetries = 3;
private const string DefaultKey = "default";
```

### Code Formatting

```csharp
// Indentation: Use 4 spaces (not tabs)
public class Example
{
    public void Method()
    {
        if (condition)
        {
            DoSomething();
        }
    }
}

// Braces: Allman style (opening brace on new line)
public void Method()
{
    if (condition)
    {
        // code
    }
}

// Line length: Keep lines under 120 characters
// Use line breaks for long statements
var result = this.CalculateValue(parameter1, parameter2)
    .Filter(x => x.IsValid)
    .OrderBy(x => x.Name)
    .ToList();
```

### Access Modifiers

```csharp
// Always specify access modifiers explicitly
public class Example
{
    // Public members
    public void PublicMethod() { }
    
    // Protected members for inheritance
    protected void ProtectedMethod() { }
    
    // Internal for same assembly
    internal void InternalMethod() { }
    
    // Private for encapsulation (default for fields/properties)
    private void PrivateMethod() { }
    private string _privateField;
}
```

### LINQ and Modern C# Features

```csharp
// Use LINQ for collections
var activeUsers = users.Where(u => u.IsActive)
    .OrderBy(u => u.Name)
    .ToList();

// Use string interpolation
string message = $"Hello {firstName} {lastName}";

// Use null-coalescing operators
var name = person?.Name ?? "Unknown";

// Use null-conditional operators
var email = user?.Email?.ToLower();

// Use expression-bodied members when appropriate
public string FullName => $"{FirstName} {LastName}";
public bool IsValid => !string.IsNullOrEmpty(Name);
```

### Comments and Documentation

```csharp
// Use XML documentation comments for public members
/// <summary>
/// Calculates the total amount for the given items.
/// </summary>
/// <param name="items">The items to calculate</param>
/// <returns>The calculated total amount</returns>
/// <exception cref="ArgumentNullException">Thrown when items is null</exception>
public decimal CalculateTotal(List<Item> items)
{
    // Inline comments for complex logic
    // Start with // and a space
    var total = 0m;
    
    foreach (var item in items)
    {
        total += item.Price * item.Quantity;
    }
    
    return total;
}

// Avoid obvious comments
// BAD: Increment i
// i++;

// GOOD: Process each user sequentially
foreach (var user in users)
{
    user.Process();
}
```

### Exception Handling

```csharp
// Always catch specific exceptions
try
{
    var result = ProcessData(data);
}
catch (ArgumentNullException ex)
{
    _logger.LogError($"Invalid data: {ex.Message}");
    throw;
}
catch (InvalidOperationException ex)
{
    _logger.LogWarning($"Operation failed: {ex.Message}");
    // Handle gracefully
}

// Use proper exception messages
throw new ArgumentNullException(nameof(user), "User cannot be null");
```

### Async/Await

```csharp
// Use async/await for asynchronous operations
public async Task<User> GetUserAsync(int userId)
{
    return await _repository.GetUserAsync(userId);
}

// Always use ConfigureAwait(false) in library code
var result = await service.FetchDataAsync()
    .ConfigureAwait(false);

// Use Task and Task<T>, not void for async methods
// Exception: Event handlers may use async void
public async Task<string> FetchAsync() { }
```

### SOLID Principles

```csharp
// Single Responsibility: Each class has one reason to change
public class UserRepository { }
public class UserValidator { }

// Open/Closed: Open for extension, closed for modification
public abstract class BaseRepository { }
public class UserRepository : BaseRepository { }

// Liskov Substitution: Derived classes should be substitutable
public interface IRepository<T> { }

// Interface Segregation: Many specific interfaces over general ones
public interface IReadRepository { }
public interface IWriteRepository { }

// Dependency Inversion: Depend on abstractions, not concrete implementations
public class UserService
{
    private readonly IUserRepository _repository;
    
    public UserService(IUserRepository repository)
    {
        _repository = repository;
    }
}
```

## Commit Message Guidelines

### Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Type

- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation only changes
- `style`: Changes that don't affect code meaning (whitespace, formatting, etc.)
- `refactor`: Code change that neither fixes a bug nor adds a feature
- `perf`: Code change that improves performance
- `test`: Adding missing tests or correcting existing tests
- `chore`: Changes to build process, dependencies, or tooling

### Examples

```
feat(user-management): add email verification endpoint

fix(repair-orders): resolve date parsing issue in order list

docs(contributing): update setup instructions

refactor(authentication): simplify token validation logic

perf(database): add indexes to improve query performance
```

## Getting Help

- Check the [Documentation](./README.md)
- Open an [Issue](https://github.com/AB-Repair-Manager/ab-repair-manager/issues)
- Join our community discussions
- Contact the maintainers

## License

By contributing to this project, you agree that your contributions will be licensed under the same license as the project (see LICENSE file for details).

---

Thank you for contributing to AB Repair Manager! We appreciate your effort and support.
