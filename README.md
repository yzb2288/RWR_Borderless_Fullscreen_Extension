# RWR_Borderless_Fullscreen_Extension

Set RUNNING WITH RIFLES game window to borderless fullscreen mode.

If you have access to the game source code, you can add these lines to game window starting code and then it can achieve the same feature:

```cpp
// need to add a new borderless fullscreen config value to rwr_config.exe
if (get_game_config_fullscreen_mode() == BORDERLESS_FULLSCREEN)
{
    LONG game_window_style = GetWindowLong(g_hwnd, GWL_STYLE);
    game_window_style &= ~(WS_BORDER | WS_DLGFRAME | WS_SYSMENU | WS_THICKFRAME | WS_MINIMIZEBOX);
    SetWindowLong(g_hwnd, GWL_STYLE, game_window_style);
}
```
