# Sample code to reproduce a .NET MAUI Button bug where it doesn't draw borders

### Description

The Button.BorderColor property does not seem to work on some platforms. Adding `BorderColor="Black"` to the XAML for a Button control seems to have no effect on macOS or Android.

### Steps to Reproduce

Create a new .NET MAUI app and replace the contents of MainPage.xaml with this:

```
    <HorizontalStackLayout>
        <Button BackgroundColor="LightBlue" BorderColor="Black" HeightRequest="100" WidthRequest="100" />
        <Button BackgroundColor="LightBlue" HeightRequest="100" WidthRequest="100" />
        <Button BackgroundColor="LightBlue" BorderColor="Black" HeightRequest="100" WidthRequest="100" />
    </HorizontalStackLayout>
```

and remove the OnCounterClicked method from MainPage.xaml.cs. 


Run the app on macOS:

`dotnet build -t:Run -f net8.0-maccatalyst`

The borders do not show up on the buttons with `BorderColor="Black"`:

<img width="658" alt="image" src="https://github.com/dotnet/maui/assets/7516297/89e110a1-2af1-4fee-b240-bc7bdda41ceb">

They don't show up on Android either:

![image](https://github.com/dotnet/maui/assets/7516297/3f660045-d121-48ba-b31f-cb0ca7e3ed5a)

Here's the same XAML rendered in Windows—it works correctly:

<img width="609" alt="image" src="https://github.com/dotnet/maui/assets/7516297/1e522920-3c05-49fa-8600-0c32d0cc2370">


### Link to public reproduction project repository

https://github.com/andrewstellman/reproduce-maui-button-border-bug

### Version with bug

8.0.0-rc.2.9373

### Is this a regression from previous behavior?

Not sure, did not test other versions

### Last version that worked well

Unknown/Other

### Affected platforms

Android, macOS

### Affected platform versions

_No response_

### Did you find any workaround?

_No response_

### Relevant log output

_No response_
