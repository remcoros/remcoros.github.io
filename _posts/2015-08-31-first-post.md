---
layout: post
title: First post
tags: [programming]
---

First post.

```csharp
try
{
    var width = screen.Width;
    var height = screen.Height;
    var bitmapData = screen.CapturedBitmap;
    var img = new Bitmap(width, height, PixelFormat.Format32bppRgb);
    var bmpData = img.LockBits(new Rectangle(0, 0, img.Width, img.Height), ImageLockMode.WriteOnly, img.PixelFormat);

    Marshal.Copy(bitmapData, 0, bmpData.Scan0, bitmapData.Length);
    img.UnlockBits(bmpData);

    result = new ScreenshotResource(img);
}
catch (Exception ex)
{
    Log.Debug(ex, "Error decoding DirectX pixels: {0}");
    return null;
}
```