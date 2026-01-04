# How to Get the Node in WPF TreeView?

This sample illustrates how to get the node in [WPF TreeView](https://www.syncfusion.com/wpf-controls/treeview) (SfTreeView).

# About the sample

In `SfTreeView`, you can get the node based on the item bound with it using `SfTreeView.GetItemInfo` method.

#### XAML

``` xml
<syncfusion:SfTreeView x:Name="sfTreeView" Grid.Row="1"  ExpandActionTrigger="Node"  AutoExpandMode="AllNodes"
                               ChildPropertyName="SubFiles"
                               FullRowSelect="True"
                               ItemsSource="{Binding ImageNodeInfo}">
            <syncfusion:SfTreeView.ItemTemplate>
                <DataTemplate>
                    <Grid x:Name="grid">
                        <Grid Grid.Row="0">
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="20" />
                                <ColumnDefinition Width="*" />
                            </Grid.ColumnDefinitions>
                            <Grid>
                                <Image Source="{Binding ImageIcon}"
                                       VerticalAlignment="Center"
                                       HorizontalAlignment="Center"
                                       Height="16"
                                       Width="16"/>
                            </Grid>
                            <Grid Grid.Column="1"
                                  Margin="1,0,0,0"
                                  VerticalAlignment="Center">
                                <TextBlock Text="{Binding ItemName}"
                                           Foreground="Black"
                                           FontSize="13"
                                           VerticalAlignment="Center" />
                            </Grid>
                        </Grid>
                    </Grid>
                </DataTemplate>
            </syncfusion:SfTreeView.ItemTemplate>
</syncfusion:SfTreeView>
```

#### C#

```c#
var treeViewInfo = sfTreeView.GetItemInfo((this.DataContext as FileManagerViewModel).ImageNodeInfo.FirstOrDefault(x => x.ItemName == "Documents"));
var node = treeViewInfo.Node;
```

## Requirements to run the demo
 Visual Studio 2015 and above versions
