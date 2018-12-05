---
title: Using Edy Viewer on English Windows 10
---

While in Japan, my University issued me an Edy card. Rakuten Edy is a prepaid stored-value contactless smart card, which uses Sony's FeliCa technology. I bought the [Sony RC-S380 reader](https://www.sony.co.jp/Products/felica/consumer/products/RC-S380.html) ([Amazon](https://www.amazon.co.jp/ソニー-SONY-非接触ICカードリーダー-PaSoRi-RC-S380/dp/B00948CGAG/)) to use for it and other FeliCa cards. When you first plug it in, the default Windows 10 drivers allow it to be used as a standard NFC reader and it can do things like receive information from Android phones. But to use it with FeliCa cards you need to install [Sony's software](https://www.sony.co.jp/Products/felica/consumer/download/felicaportsoftware.html) (which does remove some of the generic NFC functionality). 

Now, to use Edy Viewer and other FeliCa things on the web, you need to use Internet Explorer and the software from Sony should have installed an add-on for it called "CFeliCaAccessor Object". But the issue comes when you install this software on English Windows 10 (the issue seems to be because of it being in English, it happens on English Windows 7 too, but it may also have to do with Windows 10 in general and may also happen when running Windows 10 in Japanese), the installer does not install this addon unless it detects its on Japanese Windows.

I was able to figure out the solution thanks to [this blog post](https://backofthelid.com/windows10/edy/). You need to restore the `FSC2.dll` file in `C:\Program Files (x86)\Sony\FeliCa Secure Client\bin\`. After getting this file, run `regsvr32 "C:\Program Files (x86)\Sony\FeliCa Secure Client\bin\FSC2.dll"` in an administrator command prompt. After that you should be able to use the add-on in Internet Explorer.

To get this DLL file, I created a Windows 7 VM and set the language/region to Japanese. Then I installed the Sony software which this time used the Japanese installer and installed the file needed. 

I have uploaded the `FSC2.dll` file [here](https://mega.nz/#!9I92ASLL!3_h49BOHVR4aLFoUR5I0oF_xC85Vwhvl-d8srul5VQw).
