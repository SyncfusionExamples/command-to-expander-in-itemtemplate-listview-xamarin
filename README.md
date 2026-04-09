**[View document in Syncfusion Xamarin Knowledge base](https://www.syncfusion.com/kb/12154/how-to-bind-command-to-expander-in-itemtemplate-of-xamarin-forms-listview-sflistview)**

## Sample

```xaml
<sflistview:SfListView x:Name="listView" AutoFitMode="DynamicHeight" ItemsSource="{Binding ContactsInfo}">
    <sflistview:SfListView.ItemTemplate>
        <DataTemplate>
                <Grid Padding="{OnPlatform Android=2, iOS=2,  UWP=0}" Margin="{OnPlatform Android=1, iOS=1,  UWP=0}" BackgroundColor="White" >
                    <expander:SfExpander x:Name="expander" HeaderIconPosition="None">
                        <expander:SfExpander.Header>
                            <code>
                            . . .
                            . . .
                            <code>
                        </expander:SfExpander.Header>
                        <expander:SfExpander.Content>
                            <code>
                            . . .
                            . . .
                            <code>
                        </expander:SfExpander.Content>
                    </expander:SfExpander>
                </Grid>
        </DataTemplate>
    </sflistview:SfListView.ItemTemplate>
</sflistview:SfListView>

C#:

public static readonly BindableProperty EventNameProperty = BindableProperty.Create ("EventName", typeof(string), typeof(EventToCommandBehavior), null, propertyChanged: OnEventNameChanged);
public static readonly BindableProperty CommandProperty = BindableProperty.Create ("Command", typeof(ICommand), typeof(EventToCommandBehavior), null);
public static readonly BindableProperty CommandParameterProperty = BindableProperty.Create ("CommandParameter", typeof(object), typeof(EventToCommandBehavior), null);
public static readonly BindableProperty InputConverterProperty = BindableProperty.Create ("Converter", typeof(IValueConverter), typeof(EventToCommandBehavior), null);

public string EventName {
    get { return (string)GetValue (EventNameProperty); }
    set { SetValue (EventNameProperty, value); }
}

public ICommand Command {
    get { return (ICommand)GetValue (CommandProperty); }
    set { SetValue (CommandProperty, value); }
}

public object CommandParameter {
    get { return GetValue (CommandParameterProperty); }
    set { SetValue (CommandParameterProperty, value); }
}

public IValueConverter Converter {
    get { return (IValueConverter)GetValue (InputConverterProperty); }
    set { SetValue (InputConverterProperty, value); }
}
```
