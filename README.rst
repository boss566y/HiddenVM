|foo|

.. |foo| raw:: html

    <a href="#About"><img src="./misc/hiddenvm-logo-full.svg" width="100%" height="184pt"></a>
    <p align="center"><a href="#About"><img src="https://dummyimage.com/1x45/ffffff/ffffff.png" /></a> <a href="#About"><img src="https://img.shields.io/github/v/release/aforensics/HiddenVM.svg?color=%2344cc11ff&label=version" /></a>&nbsp; <a href="#About"><img src="https://camo.githubusercontent.com/bf135a9cea09d0ea4bba410582c0e70ec8222736/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4c6963656e73652d47504c25323076332d626c75652e737667" /></a>&nbsp; <a href="#About"><img src="https://img.shields.io/github/downloads/aforensics/HiddenVM/total?color=%236b2981" /></a>&nbsp; <a href="#About"><img src="https://img.shields.io/github/stars/aforensics/HiddenVM.svg?label=github%20stars" /></a> <a href="#About"><img src="https://dummyimage.com/1x45/ffffff/ffffff.png" /></a></p>

.. raw:: html

    <h2><a href="#About">HiddenVM</a></h2>

PLEASE NOTE: If at any time Tails pushes an unexpected update, and HiddenVM is not yet updated for it, and you are stuck with a new Tails and no working HiddenVM version, you can re-download and temporarily use an earlier version of Tails until HiddenVM is updated. There are `archived direct HTTP download mirrors of Tails images <https://web.archive.org/https://mirrors.edge.kernel.org/tails/stable/>`_, `archived official torrents with PGP signatures <https://web.archive.org/https://tails.net/torrents/files/>`_, or third party archives at linuxtracker.org or fosstorrents.com etc. (Always verify third party torrents with archived official PGP sigs for safety.) Unless there is a known security vulnerability patched by the new Tails which actually affects how you use Tails, doing a temporary downgrade is not unsafe. You aren't necessarily unsafe by using older-than-one-month-old Tails software for a short time. Thank you for your patience, and stay safe.

.. contents::

About
----------------------

**HiddenVM** is an innovation in computing privacy.

Imagine you're entering a country at the airport. The border agents seize your laptop and force you to unlock it so that they can violate your privacy, treat you like a criminal, and `insult your humanity <https://www.reddit.com/r/privacy/comments/epblc8/australian_border_employee_hands_phone_back_to/>`_. Is that the world you want to live in?

Whether you use Windows, macOS or Linux, now there's a tech solution for better privacy: **HiddenVM**.

**HiddenVM** is a simple, one-click, free and open-source Linux application that allows you to run Oracle's open-source `VirtualBox software <https://virtualbox.org>`_ on the `Tails operating system <https://tails.net/>`_.

This means you can run almost any OS as a VM inside the most anti-forensic computing environment in the world. Works where Tails does.

The VM will even connect to full-speed pre-Tor Internet by default, while leaving the Tor connection in Tails undisturbed.

To ensure anti-forensic deniability of your VMs, you can place your persistent HiddenVM installation - containing all VirtualBox binaries, VMs, and HiddenVM itself - in a `hidden VeraCrypt volume <https://www.veracrypt.fr/en/Hidden%20Volume.html>`_\ , and only mount it in the amnesic Tails.

If you set it up correctly, when your computer is turned off all anyone can plausibly see is a blank Tails USB and a 'wiped' hard drive full of meaningless data, or a default booting decoy OS in a partition that you can create.

How does it feel to have *no* trace of your entire operating system - whether it's Windows, macOS or Linux - ever touch your hard drive? Now you can find out.

HiddenVM: *insanely private!*

Installation and usage
----------------------

**Before you install:**

* 
  Always have two Tails USB sticks, with one as a backup of the latest working Tails for your current HiddenVM.

* 
  Always upgrade Tails on your second stick, in case the new Tails doesn't work with your current HiddenVM.

*
  Always give us time to troubleshoot and fix our code to make it work with a new Tails version. Thank you for your patience.

*
  This will give you stability and prevent you from being locked out of your HiddenVM at any point due to a Tails upgrade.

**Install:**

* 
  Boot into `Tails <https://tails.net>`_ on your computer and set an `admin password <https://tails.net/doc/first_steps/welcome_screen/administration_password/index.en.html>`_ for your session.

* 
  `Do NOT use <#why-shouldnt-i-use-tails-official-persistent-volume-feature>`_ Tails' `persistent volume feature <hhttps://tails.net/doc/persistent_storage/index.en.html>`_.

* 
  Create and mount a deniable, secure storage environment on internal or external media such as a `VeraCrypt <https://veracrypt.fr/en>`_ volume.

* 
  \ `Download our latest release ZIP <https://github.com/aforensics/HiddenVM/releases>`_\  and extract the archive.

* 
  Run our AppImage file in the Files browser.

* 
  Choose to store HiddenVM in your secure storage and it will download all binaries to launch VirtualBox.

**Usage:**

* 
  After initially installing HiddenVM you can use it offline where each VirtualBox launch takes about 2 minutes.

How can I trust the HiddenVM AppImage file?
-------------------------------------------

**You don't have to. Inspect the AppImage code:**


* 
  Open a Terminal and ``cd`` to the folder containing our AppImage.

* 
  Run ``mkdir inspect && sudo mount HiddenVM-*-x86_64.AppImage inspect -o offset=188456``

* 
  Every file in the mounted folder can be inspected with a text editor. To search for IP addresses or web domains that HiddenVM could try to phone home to and violate your privacy, use `Searchmonkey <http://searchmonkey.embeddediq.com>`_ (\ ``sudo apt install searchmonkey``\ ) to recursively search for ``\.\S`` in the mounted folder's files.

* 
  Once you trust the current version of HiddenVM, when new releases arrive you can track code changes by using `Meld <https://meldmerge.org>`_ (\ ``sudo apt install meld``\ ). Drag and drop the old and new folders together into *Meld*\ , and any code differences will be highlighted.

**Also you can check the integrity of our ZIP release file:**


* 
  Download both our ZIP and the SHA512.

* 
  Extract our AppImage and place it next to the SHA512.

* 
  Do ``sha512sum -c HiddenVM-*-x86_64.sha512`` and it will check both the ZIP and the AppImage.

**Or generate your own AppImage from our source code once you trust it:**


#. 
   ``git clone https://github.com/boss566y/HiddenVM.git``

#. 
   ``cd HiddenVM/appimage``

#. 
   ``./make-appimage.sh`` (The script will download **appimagetool** from `AppImageKit <https://github.com/AppImage/AppImageKit>`_ if it needs to.)

See your own generated AppImage in the ``target`` subdir.

FAQs / Warnings
---------------

See orignal FAQ on https://github.com/aforensics/HiddenVM

Disclaimer
----------

Despite the grand words earlier in this README, any software project claiming increased security, privacy or anonymity can never provide a guarantee for such things, and we are no different here.

As the license states, we are not liable to you for any damages as a result of using our software. Similarly, any claims by our project or its representatives are personal opinions and do not constitute legal advice or digital security advice.

The HiddenVM project provides no guarantee of any security, privacy or anonymity as a result of you using our software. You use our software at your own risk, and if or how you use it is your own discretion.
