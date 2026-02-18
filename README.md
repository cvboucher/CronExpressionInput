# CronExpressionInput

Blazor component for editing cron expressions (from scratch).

## Features

- Works in Blazor Server and Blazor WebAssembly
- Dual input: full expression + individual fields
- Optional seconds and year fields

## Install (project reference)

```bash
# From your solution directory
 dotnet add <YourApp>.csproj reference ./CronExpressionInput/CronExpressionInput.csproj
```

## Usage

> Requires Radzen components. Add `Radzen.Blazor` and register `DialogService` in your host app.

```razor
@using CronExpressionInput
@using Radzen

<CronExpressionInput @bind-Value="Cron" />

@code {
    private string Cron { get; set; } = "0 9 * * 1-5";
}
```

### Host app setup

```csharp
builder.Services.AddScoped<DialogService>();
```

```razor
<RadzenDialog />
```

### Optional parameters

```razor
<CronExpressionInput @bind-Value="Cron"
                    ShowSeconds="true"
                    IncludeYear="false"
                    Disabled="false"
                    Class="my-cron" />
```

## Styling

The component ships with scoped CSS in `CronExpressionInput.razor.css`. You can override styles by targeting:

- `.cron-expression-input`
- `.cron-expression`
- `.cron-fields`
- `.cron-field`
- `.cron-field-input`

## Notes

This component does not validate cron syntax; it keeps the fields in sync and emits the combined expression.
