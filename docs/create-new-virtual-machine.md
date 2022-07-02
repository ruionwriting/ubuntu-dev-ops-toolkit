# Create new virtual machine

When completing these instructions you are ready to power on a new virtual machine and to install the operating system (I'll be using Ubuntu in these guides) that you can then configure using the various guides, scripts I provide or your own additions. It's a clean baseline that we can snapshot and evolve according our own needs/preferences.

> **Note**
> This guide assumes that you have a valid paid VMWare license. Player editions might work as well but it's something I've not tested as I favour using the Pro versions.
>
> You see that I'll be using fairly generous resources for my guest as this guide is more oriented to provide a complete development environment capable of running Docker and even nested virtualisation. Dependending on your needs you can later, following the setup instructions, add less or more resources.

Open VMware Workstation Pro or VMware Fusion Pro and hit `Create a New Virtual Machine`:

> **Note**
> I'm using Windows 11 as my host operating system but similar screens/experience expected for macOS (VMware Fusion Pro) and Linux (VMware Workstation Pro).

![image](https://user-images.githubusercontent.com/1220067/177008595-4bd5f026-6ecf-4f0c-9319-520c894c7441.png)

We choose `Custom (advanced)` then hit `Next`. Compatibility we accept defaults:

![image](https://user-images.githubusercontent.com/1220067/177008680-98b732e8-c8af-4197-a51e-df6c7adabbd0.png)

> **Note**
> Before proceeding ensure that you have your prefered Ubuntu ISO already downloaded - I recommend always to use the latest LTS version. Go to [Download Ubuntu Desktop](https://ubuntu.com/download/desktop) and download the default edition or use the [Alternative downloads](https://ubuntu.com/download/alternative-downloads).
>
> In this guide I use [Kubuntu](https://kubuntu.org/getkubuntu/) from [Ubuntu flavours](https://ubuntu.com/desktop/flavours), its a personal preference so choose what you feel more confortable with.

I favor to have more control over the operating system install so I'll be installing it later:

![image](https://user-images.githubusercontent.com/1220067/177009120-a1c61819-f955-4a02-97c4-8e60f49eda4b.png)

We choose `I will install the operating system later. ...` then hit `Next`. Next comes the guest operating system selection:

![image](https://user-images.githubusercontent.com/1220067/177009254-a4064569-8029-4910-8aa8-253475be1067.png)

We choose `Linux` and _Version_ we select `Ubuntu 64-bit`. Next we name the virtual machine and set its location:

![image](https://user-images.githubusercontent.com/1220067/177009382-e7fac0ed-ba50-463a-8584-5a1e37747bdc.png)

Hit `Next`. Now the processor configuration:

![image](https://user-images.githubusercontent.com/1220067/177009535-f1e52820-8a18-4c31-8b82-d4acba35b207.png)

Hit `Next`. Set memory:

![image](https://user-images.githubusercontent.com/1220067/177009995-11d021e2-e3da-4a01-bb9e-07fa38b86213.png)

Hit `Next`. Now the network type using default:

![image](https://user-images.githubusercontent.com/1220067/177010053-a2bd2501-a142-48f6-b7a1-dec3c7dffffc.png)

Hit `Next`. I/O setting the recommended:

![image](https://user-images.githubusercontent.com/1220067/177010147-9018cce4-b6e0-42be-9196-43a4d0b75b1b.png)

Hit `Next`. The next steps will give us a virtual disk:

![image](https://user-images.githubusercontent.com/1220067/177010195-7870b146-b0ff-49f4-a3ed-bcc52a823fc8.png)

Hit `Next`. We setup now the capacity:

> ** Note**
> I favor not to use the defaults here as this guide main focus is to have a fully-working Linux desktop for productivity - performance is crucial.

![image](https://user-images.githubusercontent.com/1220067/177010367-a4a8f6ad-c235-4d31-8385-14074d7a5db8.png)

Changes:

* _Maximum disk size (GB)_ set to `120`, it can be less for your needs. If you plan to used this VM for nested virtualisation I would recommend `256` or `512`
* I select _Allocate all disk space now_ and
* _Store virtual disk as a single file_

Hit `Next`. I specify the location:

![image](https://user-images.githubusercontent.com/1220067/177010437-53a7123b-9d2a-4b23-b756-5c516e68cbeb.png)

Adjust the path according to your preference and hit `Next`. We're almost and it's time to customize the harware:

![image](https://user-images.githubusercontent.com/1220067/177010481-a528991a-0bd2-4e52-a695-6bafadfbce4c.png)

Hit `Customize Hardware ...`. Now:

* Select _Processors_ and tick _Virtualize Intel VT-x/EPT or AMD-V/RV1_ under _Virtualization engine_. This is required for nested virtualisation
* Select _New CD/DVD (SATA)_ and select your ISO image file. This is required for the operating install
* Select _Display_ and ensure that _Accelerate 3D graphics_ is ticked, _Graphics memory_ is set to the maximum and that the _Stretch mode_ is set to _Keep aspect ratio stretch_

Hit `Close` and then hit `Finish`. The VM will be now created:

![image](https://user-images.githubusercontent.com/1220067/177010753-4677a7d0-c4bd-481a-b477-42c1b1767adc.png)

We're now ready to power on the new virtual machine and proceed with the operating system setup.
