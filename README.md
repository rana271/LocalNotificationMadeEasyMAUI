Project Setup crate new MAUi project 
Implementation add Nuget Plugin.LocalNotification resposnible for local notification
add in MAUIProgram.cs as middle ware below line
.UseLocalNotification()
in button click events add below code
private void OnCounterClicked(object sender, EventArgs e)
	{
        var request = new NotificationRequest
        {
            NotificationId = 1000,
            Title = "Subscribe for me",
            Subtitle = "Hello Friends",
            Description = "Stay Tuned",
            BadgeNumber = 42,
            Schedule = new NotificationRequestSchedule
            {
                NotifyTime = DateTime.Now.AddSeconds(5),
                NotifyRepeatInterval = TimeSpan.FromDays(1)
            }
        };
        LocalNotificationCenter.Current.Show(request);
    }
