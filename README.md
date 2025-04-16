You can set a desired framerate in App.cpp by editing `XBOX_UWP_VRR_DemoMain.cpp`:
```cpp
	m_timer.SetFixedTimeStep(true);
	m_timer.SetTargetElapsedSeconds(1.0 / 53);
```

This will set the framerate to 53 FPS. You can change the value to any desired framerate. 

Set `SetFixedTimeStep` to `false` if you want to uncap the framerate.
```cpp
	m_timer.SetFixedTimeStep(false);
```

---

`DeviceResources.cpp`:

You can force vsync or enable/disable tearing support by changing the initial values in the constructor
```cpp
	m_vsync(true); // forces vsync and disables tearing support (=> Present1(1,0)) and no swapchain tearing flag set
	m_tearingSupport(false); // in combination with vsync off this adds the tearing flag to the swapchain presents with tearing support
```
