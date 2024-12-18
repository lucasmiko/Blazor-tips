🧠 **Quick Tip - Blazor**

**Using `CaptureUnmatchedValues`**

Did you know you can make your Blazor components more flexible by capturing unmatched HTML attributes? The `CaptureUnmatchedValues` parameter lets you pass any HTML attribute to your component without explicitly defining each one.

### When to Use:
- When you need to pass multiple HTML attributes like `id`, `class`, `onclick`, etc., to a component.
- To make your components more reusable and adaptable.

### How to Use:
1. Define a parameter with `CaptureUnmatchedValues = true`.
2. Use the `@attributes` directive to apply these attributes to the HTML element.

### Example:
CustomButton.razor:

```
<button @attributes="Atbt">@Child</button>

@code {
    [Parameter]
    public RenderFragment Child { get; set; }
    [Parameter(CaptureUnmatchedValues = true)]
    public Dictionary<string, object> Atbt { get; set; }
}
```

Usage:
```
<CustomButton id="myButton" class="btn" onclick="alert('Button clicked!')">My button</CustomButton>
```

This approach ensures your component can handle any HTML attribute dynamically, making it super flexible and reusable.


