So, for some reasons my PC can't go on sleep mode, so for disabling it i used this command

```
sudo pmset -a sleep 0; sudo pmset -a hibernatemode 0; sudo pmset -a disablesleep 1;
```

After doing this command you will see that in the macOS power menu the sleep option is disabled

![DisabledSleep](https://github.com/Bildcraft1/lenovo-idepad-15ibd-hackintosh/blob/main/.assets/images/DisableSleep.png)
