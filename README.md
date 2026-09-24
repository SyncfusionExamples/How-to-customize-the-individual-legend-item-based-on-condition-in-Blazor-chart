# Customize Individual Legend Items Conditionally in Syncfusion Blazor Accumulation Chart

## Overview

This sample demonstrates how to customize individual legend items in a Syncfusion [Blazor Charts](https://www.syncfusion.com/blazor-components/blazor-charts) accumulation chart based on runtime conditions. The implementation uses the `OnLegendItemRender` event to intercept legend rendering and apply different colors and shapes to specific legend entries according to the associated browser category. This approach helps visually group related data points and improves legend readability by making important categories easier to identify. The sample uses browser usage statistics displayed in an accumulation chart and dynamically customizes each legend item before rendering.

## Key Features

- Uses the `SfAccumulationChart` component to display browser statistics.
- Configures an `AccumulationChartSeries` with:
  - `DataSource`
  - `XName`
  - `YName`
  - `Name`
- Enables legend display using `AccumulationChartLegendSettings`.
- Handles the `OnLegendItemRender` event through a custom `LegendRender` method.
- Uses `AccumulationLegendRenderEventArgs` to customize legend items dynamically.
- Updates the `Fill` property to apply conditional legend colors.
- Updates the `Shape` property to apply conditional legend shapes.
- Demonstrates multiple `LegendShape` values, including:
  - `Diamond`
  - `Circle`
  - `InvertedTriangle`
- Applies custom legend styling based on the legend item's `Text` value.

## Prerequisites

- [Visual Studio 2022](https://visualstudio.microsoft.com/vs/) or [Visual Studio Code](https://code.visualstudio.com/)
- [.NET SDK](https://dotnet.microsoft.com/en-us/download/dotnet) compatible with the project's target framework

## How to Run the Project

**Visual Studio 2022**

1. Clone or download this repository.
2. Open the `LegendCustomization.csproj` project file.
3. Restore the required NuGet packages.
4. Build the project.
5. Run the application using `Ctrl+F5`.

**Visual Studio Code**

1. Clone or download this repository.
2. Open the repository folder in Visual Studio Code.
3. Open the integrated terminal.
4. Navigate to the project directory that contains `LegendCustomization.csproj`.

```bash
dotnet restore
dotnet run
```

5. Open the local application URL displayed in the terminal after the application starts.

## Project Structure

`LegendCustomization/Pages/Index.razor` - Main sample page containing the accumulation chart, browser statistics data source, and legend customization logic implemented through the `OnLegendItemRender` event.

## Support and Feedback

- For general product questions, visit the [Syncfusion Community Forum](https://www.syncfusion.com/forums) or [Syncfusion Support](https://www.syncfusion.com/support).
- To report an issue specific to this sample, open a GitHub issue in this repository.
- Documentation: https://help.syncfusion.com/chart-sdk/blazor/accumulation-chart/legend

## License

This is a Syncfusion sample project provided to demonstrate product usage. Review the [Syncfusion license terms](https://www.syncfusion.com/sales/pricing?category=ui-components) before using Syncfusion components in your own applications.