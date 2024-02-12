# Tkinter Dark Title bar

## Tkinter Dark Mode Main Window

Using the code below to make the title bar of the main window dark :

```py
import ctypes as ct
def dark_title_bar(window):
    window.update()
    DWMWA_USE_IMMERSIVE_DARK_MODE = 20
    set_window_attribute = ct.windll.dwmapi.DwmSetWindowAttribute
    get_parent = ct.windll.user32.GetParent
    hwnd = get_parent(window.winfo_id())
    rendering_policy = DWMWA_USE_IMMERSIVE_DARK_MODE
    value = 2
    value = ct.c_int(value)
    set_window_attribute(hwnd, rendering_policy, ct.byref(value), ct.sizeof(value))
```

Here is the Example :

![image](https://user-images.githubusercontent.com/50498845/216165713-a00b1b6d-cac3-4c46-8bc0-7969cc0dbfdd.png)

