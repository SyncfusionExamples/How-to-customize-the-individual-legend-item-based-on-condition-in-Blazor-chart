# How-to-customize-the-individual-legend-item-based-on-condition-in-Blazor-chart? 

This article explains how to customize the individual legend items based on condition in Blazor Chart Component.

**Customizing legend items in Blazor chart**

[Blazor Chart](https://www.syncfusion.com/blazor-components/blazor-charts) provides support for customizing legend items. You can customize the color, shape, and text of each legend item in the Blazor Chart Component.

This customization can be achieved by handling the [OnLegendItemRender](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AccumulationChartEvents.html#Syncfusion_Blazor_Charts_AccumulationChartEvents_OnLegendItemRender) event, which triggers before each legend item is rendered. 

An event handler is implemented to change the legend shape based on the X name, and this event handler is subscribed to the [OnLegendItemRender](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AccumulationChartEvents.html#Syncfusion_Blazor_Charts_AccumulationChartEvents_OnLegendItemRender) event. 

The code example below demonstrates how to customize individual legends based on conditions in a Blazor chart: 

**Index.razor**

```cshtml

@using Syncfusion.Blazor.Charts

<SfAccumulationChart Title="Mobile Browser Statistics">

    <AccumulationChartSeriesCollection>
        <AccumulationChartSeries DataSource="@StatisticsDetails" XName="Browser" YName="Users" Name="Browser">
        </AccumulationChartSeries>
    </AccumulationChartSeriesCollection>
    <AccumulationChartEvents OnLegendItemRender="@LegendRender"></AccumulationChartEvents>
    <AccumulationChartLegendSettings Visible="true" Position="LegendPosition.Top"></AccumulationChartLegendSettings>

</SfAccumulationChart>

@code {

    public class Statistics
    {
        public string Browser { get; set; }
        public double Users { get; set; }
    }

    public List<Statistics> StatisticsDetails = new List<Statistics>
    {
        new Statistics { Browser = "Chrome", Users = 37 },
        new Statistics { Browser = "UC Browser", Users = 17 },
        new Statistics { Browser = "iPhone", Users = 19 },
        new Statistics { Browser = "Others", Users = 4  },
        new Statistics { Browser = "Opera", Users = 11 },
        new Statistics { Browser = "Android", Users = 12 },
    };

    public void LegendRender(AccumulationLegendRenderEventArgs args)
    {
        if(args.Text == "Chrome" || args.Text == "UC Browser")
        {
            args.Fill = "green";
            args.Shape = LegendShape.Diamond;
        }
        if (args.Text == "iPhone" || args.Text == "Android")
        {
            args.Fill = "blue";
            args.Shape = LegendShape.Circle;
        }
        if (args.Text == "Others" || args.Text == "Opera")
        {
            args.Fill = "red";
            args.Shape = LegendShape.InvertedTriangle;
        }
    }
}

```

The following screenshot illustrates the output of the above code snippet.

**Output:**

![](/legend-customization.png) 

**Conclusion**

I hope you enjoyed learning how to customize legend items based on conditions in Blazor Chart Component.

You can refer to our [Blazor Chart feature tour](https://www.syncfusion.com/blazor-components/blazor-charts) page to know about its other groundbreaking feature representations and [documentation](https://blazor.syncfusion.com/documentation/chart/getting-started), and how to quickly get started for configuration specifications. You can also explore our [Blazor Chart example](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap5) to understand how to create and manipulate data.

For current customers, you can check out our components from the [License and Downloads](https://www.syncfusion.com/sales/teamlicense) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads/blazor) to check out our other controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums), [support portal](https://support.syncfusion.com/create), or [feedback portal](https://www.syncfusion.com/feedback/blazor-components?control=charts). We are always happy to assist you!
