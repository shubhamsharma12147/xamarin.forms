<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:listview"
             x:Class="listview.MainPage">

    

        <StackLayout>


            <ListView  ItemTapped="sss_ItemTapped" ItemSelected="sss_ItemSelected"  x:Name="sss" HasUnevenRows="True" Margin="10"  HorizontalOptions="FillAndExpand" >
                <ListView.ItemTemplate>
                    <DataTemplate>
                        <ViewCell>
                            <StackLayout Orientation="Vertical">

                                <Grid VerticalOptions="StartAndExpand">
                                    <Grid.RowDefinitions>

                                        <RowDefinition Height="Auto"/>
                                        <RowDefinition Height="Auto"/>
                                        <RowDefinition Height="Auto"/>
                                        <RowDefinition Height="Auto"/>
                                        <RowDefinition Height="Auto"/>
                                        <RowDefinition Height="Auto"/>
                                        <RowDefinition Height="Auto"/>
                                    </Grid.RowDefinitions>
                                    <Grid.ColumnDefinitions>
                                        <ColumnDefinition Width="*"/>
                                        <ColumnDefinition Width="2*"/>
                                       
                                    </Grid.ColumnDefinitions>

                                    <Label  Text="Company Name/ WO No."   Grid.Row="0" Grid.Column="0"/>
                                    <Label Text="{Binding Cname}" LineBreakMode="WordWrap"  TextColor="Black" Grid.Row="0" Grid.Column="1"/>
                                    
                                    <Label Text="Work Order No."  Grid.Row="1" Grid.Column="0"/>
                                    <Label Text="{Binding WO_no}" TextColor="Black" Grid.Row="1" Grid.Column="1"/>
                                    <Label Text="Party Name" Grid.Row="2" Grid.Column="0" />
                                    <Label Text="{Binding Pname}" TextColor="Black" Grid.Row="2" Grid.Column="1"/>
                                    <Label Text="Work Description"  Grid.Row="3" Grid.Column="0"/>
                                    <Label Text="{Binding W_description}" TextColor="Black" Grid.Row="3" Grid.Column="1"/>
                                    <Label Text="Keyword"  Grid.Row="4" Grid.Column="0"/>
                                    <Label Text="{Binding Keyword}" TextColor="Black" Grid.Row="4" Grid.Column="1"/>
                                    <Label Text="Remarks" Grid.Row="5" Grid.Column="0"/>
                                    <Label Text="{Binding Remarks}"  TextColor="Black"  Grid.Row="5" Grid.Column="1"/>
                                    <Label Text="Time"  Grid.Row="6" Grid.Column="0"/>
                                <Grid Grid.Row="6" Grid.Column="1">
                                    <Grid.ColumnDefinitions>
                                        <ColumnDefinition Width="*"/>
                                        <ColumnDefinition Width="60"/>
                                    </Grid.ColumnDefinitions>
                                    <Label Text="{Binding Time}" TextColor="Black" Grid.Row="0" Grid.Column="0"/>
                                    <Button BackgroundColor="Blue" Clicked="Button_Clicked"  TextColor="White"  FontSize="Micro" Text="Edit" Grid.Row="0" Grid.Column="1"/>
                                </Grid>
                            </Grid>
                            </StackLayout>
                        </ViewCell>

                    </DataTemplate>
                </ListView.ItemTemplate>
            </ListView>


        </StackLayout>
    
</ContentPage>

//c#code

 private void sss_ItemTapped(object sender, ItemTappedEventArgs e)
        {
            Data d = (Data)e.Item;
            Navigation.PushAsync(new Detail(d));
        }

        private void sss_ItemSelected(object sender, SelectedItemChangedEventArgs e)
        {
            ((ListView)sender).SelectedItem = null;
        }

        private void Button_Clicked(object sender, EventArgs e)
        {
            DisplayAlert("Item Selected", "you select"+ e.ToString(), "Ok");
        }
