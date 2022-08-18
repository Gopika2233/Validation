# Validation
<Page
    x:Class="Phone.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:Phone"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    mc:Ignorable="d">

    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*"/>
            <ColumnDefinition Width="*"/>
        </Grid.ColumnDefinitions>
        <TextBlock x:Name="txtPhone" Text="Mobile"  HorizontalAlignment="Right" Grid.Column="0" Grid.Row="2" />
        <TextBox  x:Name="Txt1"     Text=" " VerticalAlignment="Top"   Grid.Row="2" TextChanged="Txt1_TextChanged" Grid.Column="1"/>
        <TextBox  x:Name="Txt1"     Text=" " VerticalAlignment="Top"   Grid.Row="3" TextChanged="Txt1_TextChanged" Grid.Column="1"/>

    </Grid>
</Page>
        private void Txt1_TextChanged(object sender, TextChangedEventArgs e)
        {


            string phoneno = Txt1.Text;
            if (Txt1.Text.Length == 10)
            {
                Regex regex = new Regex("^[0-9]{10}$");

                bool valid = regex.IsMatch(phoneno);
                if (!valid)
                {
                    Txt1.Text =phoneno;
                }
                else 
                {
                    txtPhone.Text = "enter valid one";
                }
            }
        }
