# How-to-add-the-SfCheckbox-and-customize-its-appearance-in-MAUI-DataGrid

This article illustrates the customizing the appearance of the checkbox using the [.NET MAUI SfCheckBox](https://www.syncfusion.com/maui-controls/maui-checkbox) in a [.NET MAUI DataGrid](https://www.syncfusion.com/maui-controls/maui-datagrid).

The .NET MAUI DataGrid (SfDataGrid) allows you to load custom views in its [DataGridCell](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.DataGrid.DataGridCell.html) using the [DataGridTemplateColumn](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.DataGrid.DataGridTemplateColumn.html). It can be created both in XAML and in the code behind. You can load any view inside the DataGridCell by customizing the CellTemplate property of the DataGridTemplateColumn.

Within the `DataGridTemplateColumn`, you can load [SfCheckBox](https://help.syncfusion.com/maui/checkbox/getting-started) for the corresponding column and customize its appearance, including settings such as `CheckedColor`, `TickColor`, `UncheckedColor`, and other visual aspects.

**XAML:**

```xaml 
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:MauiApp1"
             xmlns:dataGrid="clr-namespace:Syncfusion.Maui.DataGrid;assembly=Syncfusion.Maui.DataGrid"
             xmlns:syncfusion="clr-namespace:Syncfusion.Maui.Buttons;assembly=Syncfusion.Maui.Buttons"
             x:Class="MauiApp1.MainPage">
    <ContentPage.BindingContext>
        <local:OrderInfoRepository/>
    </ContentPage.BindingContext>

    <dataGrid:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrderInfoCollection}" ColumnWidthMode="FitByHeader">
        <dataGrid:SfDataGrid.Columns>
            <dataGrid:DataGridTemplateColumn MappingName="IsShipped"
                                   HeaderText="Is Shipped">
                <dataGrid:DataGridTemplateColumn.CellTemplate>
                    <DataTemplate>
                        <syncfusion:SfCheckBox IsChecked="{Binding IsShipped}" CheckedColor="Red" TickColor="Yellow" UncheckedColor="DarkViolet" Margin="40,0,0,0"/>
                    </DataTemplate>
                </dataGrid:DataGridTemplateColumn.CellTemplate>
            </dataGrid:DataGridTemplateColumn>
        </dataGrid:SfDataGrid.Columns>
    </dataGrid:SfDataGrid>
</ContentPage>


```
