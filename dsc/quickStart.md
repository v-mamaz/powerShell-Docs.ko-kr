---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: dsc,powershell,configuration,setup
title: "DSC(필요한 상태 구성) 빠른 시작"
ms.openlocfilehash: 64c9cea7d65d0723e76c205aea104c3ec9423c1d
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2017
---
> <span data-ttu-id="22b80-103">적용 대상: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="22b80-103">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

# <a name="desired-state-configuration-quick-start"></a><span data-ttu-id="22b80-104">DSC(필요한 상태 구성) 빠른 시작</span><span class="sxs-lookup"><span data-stu-id="22b80-104">Desired State Configuration Quick Start</span></span>

<span data-ttu-id="22b80-105">이 연습에서는 DSC(필요한 상태 구성) 구성을 만들고 적용하는 과정을 처음부터 끝까지 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-105">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span>
<span data-ttu-id="22b80-106">여기에서 사용할 예제는 서버에 `Web-Server`(IIS) 기능을 사용하며 서버의 `intetpub\wwwroot` 디렉터리에 단순한 "Hello World" 웹 사이트 콘텐츠가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-106">The example we'll use ensures that a server has the `Web-Server` (IIS) feature enabled, and that the content for a simple "Hello World" website is present in the `intetpub\wwwroot` directory of that server.</span></span>

<span data-ttu-id="22b80-107">DSC가 무엇이며 어떻게 작동하는지에 대한 개요는 [의사 결정자를 위한 필요한 상태 구성 개요](DscForEngineers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22b80-107">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Decision Makers](DscForEngineers.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="22b80-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="22b80-108">Requirements</span></span>

<span data-ttu-id="22b80-109">이 예제를 실행하려면 Windows Server 2012 이상과 PowerShell 4.0 이상을 실행하는 컴퓨터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-109">To run this example, you will need a computer running Windows Server 2012 or later and PowerShell 4.0 or later.</span></span>

## <a name="write-and-place-the-indexhtm-file"></a><span data-ttu-id="22b80-110">index.htm 파일 작성 및 배치</span><span class="sxs-lookup"><span data-stu-id="22b80-110">Write and place the index.htm file</span></span>

<span data-ttu-id="22b80-111">먼저, 웹 사이트 콘텐츠로 사용할 HTML 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-111">First, we'll create the HTML file that we will use as the website content.</span></span>

<span data-ttu-id="22b80-112">루트 폴더에 `test`라는 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-112">In your root folder, create a folder named `test`.</span></span>

<span data-ttu-id="22b80-113">텍스트 편집기에서 다음 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-113">In a text editor, type the following text:</span></span>

```html
<head></head>
<body>
<p>Hello World!</p>
</body>
```

<span data-ttu-id="22b80-114">만들어 둔 `test` 폴더에 `index.htm`으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-114">Save this as `index.htm` in the `test` folder you created earlier.</span></span> 

## <a name="write-the-configuration"></a><span data-ttu-id="22b80-115">구성 작성</span><span class="sxs-lookup"><span data-stu-id="22b80-115">Write the configuration</span></span>

<span data-ttu-id="22b80-116">[DSC 구성](configurations.md)은 대상 컴퓨터(노트) 하나 이상의 구성 방법을 정의하는 특수한 PowerShell 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-116">A [DSC configuration](configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (nodes).</span></span>

<span data-ttu-id="22b80-117">PowerShell ISE에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-117">In the PowerShell ISE, type the following:</span></span>

```powershell
Configuration WebsiteTest {

    # Import the module that contains the resources we're using.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets this configuration will be applied to.
    Node 'localhost' {

        # The first resource block ensures that the Web-Server (IIS) feature is enabled.
        WindowsFeature WebServer {
            Ensure = "Present"
            Name =  "Web-Server"
        }

        # The second resource block ensures that the website content copied to the website root folder.
        File WebsiteContent {
            Ensure = 'Present'
            SourcePath = 'c:\test\index.htm'
            DestinationPath = 'c:\inetpub\wwwroot'
        }
    }
} 
```

<span data-ttu-id="22b80-118">파일을 `WebsiteTest.ps1`로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-118">Save the file as `WebsiteTest.ps1`.</span></span>

<span data-ttu-id="22b80-119">함수 이름 앞에 **Configuration** 키워드를 추가한 PowerShell 함수처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-119">You can see that it looks like a PowerShell function, with the addition of the keyword **Configuration** used before the name of the function.</span></span>

<span data-ttu-id="22b80-120">**Node** 블록은 구성할 대상 노드를 지정하며, 이 경우는 `localhost`입니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-120">The **Node** block specifies the target node to be configured, in this case `localhost`.</span></span>

<span data-ttu-id="22b80-121">구성에서는 [WindowsFeature](windowsFeatureResource.md) 및 [File](fileResource.md)의 두 [리소스](resources.md)를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-121">The configuration calls two [resources](resources.md), [WindowsFeature](windowsFeatureResource.md) and [File](fileResource.md).</span></span>
<span data-ttu-id="22b80-122">리소스는 대상 노드가 구성에 정의된 상태에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-122">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="22b80-123">구성 컴파일</span><span class="sxs-lookup"><span data-stu-id="22b80-123">Compile the configuration</span></span>

<span data-ttu-id="22b80-124">노드에 DSC 구성을 적용하려면 먼저 MOF 파일로 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-124">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span>
<span data-ttu-id="22b80-125">그러려면 구성을 함수처럼 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-125">To do this, you run the configuration like a function.</span></span>
<span data-ttu-id="22b80-126">PowerShell 콘솔에서 구성을 저장한 폴더로 이동한 후 다음 명령을 실행하여 구성을 MOF 파일로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-126">In a PowerShell console, navigate to the same folder where you saved your configuration and run the following commands to compile the configuration into a MOF file:</span></span>

```powershell
. .\WebsiteTest.ps1
WebsiteTest
```

<span data-ttu-id="22b80-127">그러면 다음과 같은 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-127">This generates the following output:</span></span>

```
Directory: C:\ConfigurationTest\WebsiteTest


Mode                LastWriteTime         Length Name                                                                                                                                                       
----                -------------         ------ ----                                                                                                                                                       
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

<span data-ttu-id="22b80-128">첫 번째 줄은 콘솔에서 구성 함수를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-128">The first line makes the configuration function available in the console.</span></span>
<span data-ttu-id="22b80-129">두 번째 줄은 구성을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-129">The second line runs the configuration.</span></span>
<span data-ttu-id="22b80-130">그 결과 `WebsiteTest`라는 이름의 새 폴더가 현재 폴더의 하위 폴더로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-130">The result is that a new folder, named `WebsiteTest` is created as a subfolder of the current folder.</span></span>
<span data-ttu-id="22b80-131">`WebsiteTest` 폴더에는 `localhost.mof`라는 이름의 파일이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-131">The `WebsiteTest` folder contains a file named `localhost.mof`.</span></span> <span data-ttu-id="22b80-132">이 파일을 대상 노드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-132">It is this file that can then be applied to the target node.</span></span>

## <a name="apply-the-configuration"></a><span data-ttu-id="22b80-133">구성 적용</span><span class="sxs-lookup"><span data-stu-id="22b80-133">Apply the configuration</span></span>

<span data-ttu-id="22b80-134">이제 MOF를 컴파일했으므로 [Start-DscConfiguration](/reference/5.1/PSDesiredStateConfiguration/Start-DscConfiguration.md) cmdlet을 호출하여 구성을 대상 노드(이 경우 로컬 컴퓨터)에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-134">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/reference/5.1/PSDesiredStateConfiguration/Start-DscConfiguration.md) cmdlet.</span></span>

<span data-ttu-id="22b80-135">`Start-DscConfiguration` cmdlet은 DSC의 엔진인 [LCM(로컬 구성 관리자)](metaConfig.md)에 구성을 적용하라고 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-135">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](metaConfig.md), which is the engine of DSC, to apply the configuration.</span></span>
<span data-ttu-id="22b80-136">LCM은 DSC 리소스를 호출하여 구성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-136">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

<span data-ttu-id="22b80-137">PowerShell 콘솔에서 구성을 저장한 폴더로 이동한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-137">In a PowerShell console, navigate to the same folder where you saved your configuration and run the following command:</span></span>

```powershell
Start-DscConfiguration .\WebsiteTest
```

## <a name="test-the-configuration"></a><span data-ttu-id="22b80-138">구성 테스트</span><span class="sxs-lookup"><span data-stu-id="22b80-138">Test the configuration</span></span>

<span data-ttu-id="22b80-139">[Get-DscConfigurationStatus](/reference/5.1/PSDesiredStateConfiguration/Get-DscConfigurationStatus.md) cmdlet을 호출하여 구성의 성공 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-139">You can call the [Get-DscConfigurationStatus](/reference/5.1/PSDesiredStateConfiguration/Get-DscConfigurationStatus.md) cmdlet to see whether the configuration succeeded.</span></span> 

<span data-ttu-id="22b80-140">결과를 직접 테스트할 수도 있습니다. 이 경우는 웹 브라우저에서 `http://localhost/`를 탐색하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-140">You can also test the results directly, in this case by browsing to `http://localhost/` in a web browser.</span></span> <span data-ttu-id="22b80-141">이 예제의 첫 단계에서 생성한 "Hello World" HTML 페이지가 보입니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-141">You should see the "Hello World" HTML page you created as the first step in this example.</span></span>

## <a name="next-steps"></a><span data-ttu-id="22b80-142">다음 단계</span><span class="sxs-lookup"><span data-stu-id="22b80-142">Next steps</span></span>

- <span data-ttu-id="22b80-143">DSC 구성에 대한 자세한 내용은 [DSC 구성](configurations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22b80-143">Find out more about DSC configurations at [DSC configurations](configurations.md).</span></span>
- <span data-ttu-id="22b80-144">[DSC 리소스](resources.md)에서는 어떤 DSC 리소스를 사용할 수 있으며 사용자 지정 DSC 리소스를 만드는 방법은 무엇인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-144">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](resources.md).</span></span>
- <span data-ttu-id="22b80-145">[PowerShell 갤러리](https://www.powershellgallery.com/)에서는 DSC 구성 및 리소스를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b80-145">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>


