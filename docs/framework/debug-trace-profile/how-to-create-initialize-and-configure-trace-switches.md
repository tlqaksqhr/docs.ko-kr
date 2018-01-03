---
title: "방법: 추적 스위치 만들기, 초기화 및 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- trace switches, configuring
- tracing [.NET Framework], trace switches
- switches, trace
- tracing [.NET Framework], enabling or disabling
- Web.config configuration file, trace switches
ms.assetid: 5a0e41bf-f99c-4692-8799-f89617f5bcf9
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41e41f65b82061cebc52485ed08176633c45613d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-initialize-and-configure-trace-switches"></a><span data-ttu-id="4d4a6-102">방법: 추적 스위치 만들기, 초기화 및 구성</span><span class="sxs-lookup"><span data-stu-id="4d4a6-102">How to: Create, Initialize and Configure Trace Switches</span></span>
<span data-ttu-id="4d4a6-103">추적 스위치를 사용하여 추적 출력을 활성화, 비활성화 및 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-103">Trace switches enable you to enable, disable, and filter tracing output.</span></span>  
  
<a name="create"></a>   
## <a name="creating-and-initializing-a-trace-switch"></a><span data-ttu-id="4d4a6-104">추적 스위치 만들기 및 초기화</span><span class="sxs-lookup"><span data-stu-id="4d4a6-104">Creating and initializing a trace switch</span></span>  
 <span data-ttu-id="4d4a6-105">추적 스위치를 사용하려면 먼저 만들어서 코드에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-105">In order to use trace switches, you must first create them and place them in your code.</span></span> <span data-ttu-id="4d4a6-106">스위치 개체를 만드는 데 사용할 수 있는 미리 정의된 두 개의 클래스로는 <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> 클래스와 <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-106">There are two predefined classes from which you can create switch objects: the <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> class and the <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="4d4a6-107">추적 메시지의 표시 여부에만 관심이 있으면 <xref:System.Diagnostics.BooleanSwitch>를 사용하고 추적 수준을 구분하려면 <xref:System.Diagnostics.TraceSwitch>를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-107">You would use <xref:System.Diagnostics.BooleanSwitch> if you care only about whether or not a tracing message appears; you would use <xref:System.Diagnostics.TraceSwitch> if you want to discriminate between levels of tracing.</span></span> <span data-ttu-id="4d4a6-108"><xref:System.Diagnostics.TraceSwitch>가 사용되면 개인적인 디버거 메시지를 정의한 다음 다양한 추적 수준과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-108">If you use a <xref:System.Diagnostics.TraceSwitch>, you can define your own debugging messages and associate them with different trace levels.</span></span> <span data-ttu-id="4d4a6-109">추적 또는 디버깅에 두 가지 스위치 형식을 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-109">You can use both types of switches with either tracing or debugging.</span></span> <span data-ttu-id="4d4a6-110">기본적으로 <xref:System.Diagnostics.BooleanSwitch>는 비활성화되고 <xref:System.Diagnostics.TraceSwitch>는 <xref:System.Diagnostics.TraceLevel.Off?displayProperty=nameWithType> 수준으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-110">By default, a <xref:System.Diagnostics.BooleanSwitch> is disabled and a <xref:System.Diagnostics.TraceSwitch> is set to level <xref:System.Diagnostics.TraceLevel.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4d4a6-111">추적 스위치를 만들고 이 스위치를 사용할 수 있는 코드의 모든 부분에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-111">Trace switches can be created and placed in any part of your code that might use them.</span></span>  
  
 <span data-ttu-id="4d4a6-112">코드에 추적 수준과 기타 구성 옵션을 설정할 수도 있지만 구성 파일을 사용하여 스위치의 상태를 관리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-112">Although you can set trace levels and other configuration options in code, we recommend that you use the configuration file to manage the state of your switches.</span></span> <span data-ttu-id="4d4a6-113">이것은 구성 시스템에서 스위치 구성을 관리하면 좀 더 융통성 있게 사용할 수 있기 때문입니다. 즉, 응용 프로그램을 다시 컴파일하지 않고도 다양한 스위치를 설정하거나 해제하고 수준을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-113">This is because managing the configuration of your switches in the configuration system gives you greater flexibility — you can turn on and off various switches and change levels without recompiling your application.</span></span>  
  
#### <a name="to-create-and-initialize-a-trace-switch"></a><span data-ttu-id="4d4a6-114">추적 스위치를 만들고 초기화하려면</span><span class="sxs-lookup"><span data-stu-id="4d4a6-114">To create and initialize a trace switch</span></span>  
  
1.  <span data-ttu-id="4d4a6-115">스위치를 <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> 형식 또는 <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> 형식으로 정의하고 스위치의 이름과 설명을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-115">Define a switch as either type <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> or type <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> and set the name and description of the switch.</span></span>  
  
2.  <span data-ttu-id="4d4a6-116">추적 스위치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-116">Configure your trace switch.</span></span> <span data-ttu-id="4d4a6-117">자세한 내용은 [추적 스위치 구성](#configure)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-117">For more information, see [Configuring trace switches](#configure).</span></span>  
  
     <span data-ttu-id="4d4a6-118">다음 코드에서는 각 형식당 하나씩, 두 개의 스위치를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-118">The following code creates two switches, one of each type:</span></span>  
  
    ```vb  
    Dim dataSwitch As New BooleanSwitch("Data", "DataAccess module")  
    Dim generalSwitch As New TraceSwitch("General", "Entire application")  
    ```  
  
    ```csharp  
    System.Diagnostics.BooleanSwitch dataSwitch =   
       new System.Diagnostics.BooleanSwitch("Data", "DataAccess module");  
    System.Diagnostics.TraceSwitch generalSwitch =   
       new System.Diagnostics.TraceSwitch("General",   
       "Entire application");  
    ```  
  
<a name="configure"></a>   
## <a name="configuring-trace-switches"></a><span data-ttu-id="4d4a6-119">추적 스위치 구성</span><span class="sxs-lookup"><span data-stu-id="4d4a6-119">Configuring trace switches</span></span>  
 <span data-ttu-id="4d4a6-120">응용 프로그램이 배포된 후 응용 프로그램에서 추적 스위치를 구성하여 추적 출력을 사용하거나 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-120">After your application has been distributed, you can still enable or disable trace output by configuring the trace switches in your application.</span></span> <span data-ttu-id="4d4a6-121">스위치 구성은 스위치가 초기화된 후 외부 소스에서 해당 값을 변경하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-121">Configuring a switch means changing its value from an external source after it has been initialized.</span></span> <span data-ttu-id="4d4a6-122">구성 파일을 사용하여 스위치 개체의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-122">You can change the values of the switch objects using the configuration file.</span></span> <span data-ttu-id="4d4a6-123">추적 스위치를 구성하여 설정 및 해제하거나 해당 수준을 설정하고 수신기로 전달되는 메시지의 양과 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-123">You configure a trace switch to turn it on and off, or to set its level, determining the amount and type of messages it passes along to listeners.</span></span>  
  
 <span data-ttu-id="4d4a6-124">스위치는 .config 파일을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-124">Your switches are configured using the .config file.</span></span> <span data-ttu-id="4d4a6-125">웹 응용 프로그램의 경우 프로젝트와 연결된 Web.config 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-125">For a Web application, this is the Web.config file associated with the project.</span></span> <span data-ttu-id="4d4a6-126">Windows 응용 프로그램에서 이 파일의 이름은 (응용 프로그램 이름).exe.config입니다. 배포된 응용 프로그램에서 이 파일은 실행 파일과 동일한 폴더에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-126">In a Windows application, this file is named (application name).exe.config. In a deployed application, this file must reside in the same folder as the executable.</span></span>  
  
 <span data-ttu-id="4d4a6-127">응용 프로그램은 스위치 인스턴스를 만드는 코드를 처음 실행할 때 명명된 스위치에 대한 추적 수준 정보를 구성 파일에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-127">When your application executes the code that creates an instance of a switch for the first time, it checks the configuration file for trace-level information about the named switch.</span></span> <span data-ttu-id="4d4a6-128">추적 시스템은 특정 스위치에 대해 한 번만, 즉 응용 프로그램이 스위치를 처음 만들 때만 구성 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-128">The tracing system examines the configuration file only once for any particular switch — the first time your application creates the switch.</span></span>  
  
 <span data-ttu-id="4d4a6-129">배포된 응용 프로그램에서 응용 프로그램이 실행되지 않을 때 스위치 개체를 재구성하여 추적 코드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-129">In a deployed application, you enable trace code by reconfiguring switch objects when your application is not running.</span></span> <span data-ttu-id="4d4a6-130">일반적으로 이 작업을 위해 스위치 개체를 설정 및 해제하거나 추적 수준을 변경한 다음 응용 프로그램을 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-130">Typically this involves turning the switch objects on and off or by changing the tracing levels, and then restarting your application.</span></span>  
  
 <span data-ttu-id="4d4a6-131">스위치 인스턴스를 만들 때 *displayName* 인수와 *description* 인수의 두 인수를 지정하여 초기화도 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-131">When you create an instance of a switch, you also initialize it by specifying two arguments: a *displayName* argument and a *description* argument.</span></span> <span data-ttu-id="4d4a6-132">생성자의 *displayName* 인수는 <xref:System.Diagnostics.Switch> 클래스 인스턴스의 <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=nameWithType> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-132">The *displayName* argument of the constructor sets the <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=nameWithType> property of the <xref:System.Diagnostics.Switch> class instance.</span></span> <span data-ttu-id="4d4a6-133">*displayName*은 .config 파일에서 스위치를 구성하는 데 사용되는 이름이고, *description* 인수는 스위치 및 스위치가 제어하는 메시지에 대한 간략한 설명을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-133">The *displayName* is the name that is used to configure the switch in the .config file, and the *description* argument should return a brief description of the switch and what messages it controls.</span></span>  
  
 <span data-ttu-id="4d4a6-134">구성할 스위치의 이름을 지정하는 것은 물론 스위치의 값도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-134">In addition to specifying the name of a switch to configure, you must also specify a value for the switch.</span></span> <span data-ttu-id="4d4a6-135">이 값은 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-135">This value is an Integer.</span></span> <span data-ttu-id="4d4a6-136"><xref:System.Diagnostics.BooleanSwitch>에서 값 0은 **끄기**에 해당하고 0이 아닌 값은 **켜기**에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-136">For <xref:System.Diagnostics.BooleanSwitch>, a value of 0 corresponds to **Off**, and any nonzero value corresponds to **On**.</span></span> <span data-ttu-id="4d4a6-137"><xref:System.Diagnostics.TraceSwitch>에서 0, 1, 2, 3, 4는 각각 **끄기**, **오류**, **경고**, **정보** 및 **동사**에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-137">For <xref:System.Diagnostics.TraceSwitch>, 0,1,2,3, and 4 correspond **Off**, **Error**, **Warning**, **Info**, and **Verbose**, respectively.</span></span> <span data-ttu-id="4d4a6-138">4보다 큰 숫자는 **동사**로 처리되고 0보다 작은 숫자는 **끄기**로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-138">Any number greater than 4 is treated as **Verbose**, and any number less than zero is treated as **Off**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d4a6-139">.NET Framework 버전 2.0에서는 텍스트를 사용하여 스위치의 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-139">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="4d4a6-140">예를 들어 <xref:System.Diagnostics.BooleanSwitch>에 대한 `true` 또는 <xref:System.Diagnostics.TraceSwitch>에 대한 열거형 값을 나타내는 텍스트(예: `Error`)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-140">For example, `true` for a <xref:System.Diagnostics.BooleanSwitch> or the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="4d4a6-141">`<add name="myTraceSwitch" value="Error" />` 줄은 `<add name="myTraceSwitch" value="1" />`과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-141">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
 <span data-ttu-id="4d4a6-142">최종 사용자가 응용 프로그램의 추적 스위치를 구성할 수 있으려면 응용 프로그램에서 스위치에 대한 자세한 설명서를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-142">In order for end users to be able to configure an application's trace switches, you must provide detailed documentation on the switches in your application.</span></span> <span data-ttu-id="4d4a6-143">어떤 스위치가 어떤 기능을 제어하는지 및 설정/해제하는 방법을 세부적으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-143">You should detail which switches control what and how to turn them on and off.</span></span> <span data-ttu-id="4d4a6-144">또한 주석에 적절한 도움말이 있는 .config 파일을 최종 사용자에게 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-144">You should also provide your end user with a .config file that has appropriate Help in the comments.</span></span>  
  
#### <a name="to-configure-trace-switches"></a><span data-ttu-id="4d4a6-145">추적 스위치를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="4d4a6-145">To configure trace switches</span></span>  
  
1.  <span data-ttu-id="4d4a6-146">추적 스위치를 사용하려면 [추적 스위치 만들기 및 초기화](#create) 섹션의 설명대로 추적 스위치를 만들고 코드에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-146">In order to use trace switches, you must first create them and place them in your code as described in the section [Creating and initializing a trace switch](#create).</span></span>  
  
2.  <span data-ttu-id="4d4a6-147">프로젝트에 구성 파일(app.config 또는 Web.config)이 없는 경우 **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-147">If your project does not contain a configuration file (app.config or Web.config), then from the **Project** menu, select **Add New Item**.</span></span>  
  
    -   <span data-ttu-id="4d4a6-148">**Visual Basic:** **새 항목 추가** 대화 상자에서 **응용 프로그램 구성 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-148">**Visual Basic:** In the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
         <span data-ttu-id="4d4a6-149">응용 프로그램 구성 파일이 만들어져 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-149">The application configuration file is created and opened.</span></span> <span data-ttu-id="4d4a6-150">이 파일은 루트 요소가 `<configuration>.`인 XML 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-150">This is an XML document whose root element is `<configuration>.`</span></span>  
  
    -   <span data-ttu-id="4d4a6-151">**Visual C#:** **새 항목 추가** 대화 상자에서 **XML 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-151">**Visual C#:** In the **Add New Item** dialog box, choose **XML File**.</span></span> <span data-ttu-id="4d4a6-152">이 파일 이름을 **app.config**로 지정합니다. XML 편집기에서 XML 선언 뒤에 다음 XML을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-152">Name this file **app.config**. In the XML editor, after the XML declaration, add the following XML:</span></span>  
  
        ```xml  
        <configuration>  
        </configuration>  
        ```  
  
         <span data-ttu-id="4d4a6-153">프로젝트를 컴파일하면 app.config 파일이 프로젝트 출력 폴더에 복사되고 이름이 *applicationname*.exe.config로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-153">When your project is compiled, the app.config file is copied to the project output folder and is renamed *applicationname*.exe.config.</span></span>  
  
3.  <span data-ttu-id="4d4a6-154">`<configuration>` 태그 뒤, `</configuration>` 태그 앞에 적절한 XML을 추가하여 스위치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-154">After the `<configuration>` tag but before the `</configuration>` tag, add the appropriate XML to configure your switches.</span></span> <span data-ttu-id="4d4a6-155">다음 예제에서는 **DisplayName** 속성이 `DataMessageSwitch`인 **BooleanSwitch** 및 **DisplayName** 속성이 `TraceLevelSwitch`인 **TraceSwitch**를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-155">The following examples demonstrate a **BooleanSwitch** with a **DisplayName** property of `DataMessageSwitch` and a **TraceSwitch** with a **DisplayName** property of `TraceLevelSwitch`.</span></span>  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <add name="DataMessagesSwitch" value="0" />  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
     <span data-ttu-id="4d4a6-156">이 구성에서는 두 스위치가 모두 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-156">In this configuration, both switches are off.</span></span>  
  
4.  <span data-ttu-id="4d4a6-157">이전 예제에 표시된 `DataMessagesSwitch`와 같은 **BooleanSwitch**를 설정해야 하는 경우 **Value**를 0이 아닌 임의의 정수로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-157">If you need to turn on a **BooleanSwitch**, such as `DataMessagesSwitch` shown in the previous example, change the **Value** to any integer other than 0.</span></span>  
  
5.  <span data-ttu-id="4d4a6-158">이전 예제에 표시된 `TraceLevelSwitch`와 같은 **TraceSwitch**를 설정해야 하는 경우 **Value**를 적절한 수준 설정(1-4)으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-158">If you need to turn on a **TraceSwitch**, such as `TraceLevelSwitch` shown in the previous example, change the **Value** to the appropriate level setting (1 to 4).</span></span>  
  
6.  <span data-ttu-id="4d4a6-159">최종 사용자가 스위치를 적절하게 구성하기 위해 변경할 값을 명확하게 이해할 수 있도록 .config 파일에 주석을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-159">Add comments to the .config file so the end user has a clear understanding of what values to change to configure the switches appropriately.</span></span>  
  
     <span data-ttu-id="4d4a6-160">다음 예제에서는 주석을 포함하는 최종 코드의 모양을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d4a6-160">The following example shows how the final code, including comments, might look:</span></span>  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <!-- This switch controls data messages. In order to receive data   
             trace messages, change value="0" to value="1" -->  
          <add name="DataMessagesSwitch" value="0" />  
          <!-- This switch controls general messages. In order to   
             receive general trace messages change the value to the   
             appropriate level. "1" gives error messages, "2" gives errors   
             and warnings, "3" gives more detailed error information, and   
             "4" gives verbose trace information -->  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4d4a6-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d4a6-161">See Also</span></span>  
 [<span data-ttu-id="4d4a6-162">응용 프로그램 추적 및 조율</span><span class="sxs-lookup"><span data-stu-id="4d4a6-162">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 [<span data-ttu-id="4d4a6-163">방법: 응용 프로그램 코드에 Trace 문 추가</span><span class="sxs-lookup"><span data-stu-id="4d4a6-163">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)  
 [<span data-ttu-id="4d4a6-164">추적 스위치</span><span class="sxs-lookup"><span data-stu-id="4d4a6-164">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)  
 [<span data-ttu-id="4d4a6-165">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4d4a6-165">Trace and Debug Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
