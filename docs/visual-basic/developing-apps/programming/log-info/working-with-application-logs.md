---
title: Visual Basic에서 응용 프로그램 로그 작업
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- logs, application
- application event logs, Visual Basic
- application event logs
ms.assetid: 2581afd1-5791-4bc4-86b2-46244e9fe468
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 40cad53cd9283a99a93cde79616151e77489e7bb
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="working-with-application-logs-in-visual-basic"></a><span data-ttu-id="5bc7f-102">Visual Basic에서 응용 프로그램 로그 작업</span><span class="sxs-lookup"><span data-stu-id="5bc7f-102">Working with Application Logs in Visual Basic</span></span>
<span data-ttu-id="5bc7f-103">`My.Applicaton.Log` 및 `My.Log` 개체를 사용하면 로깅 및 추적 정보를 로그에 쉽게 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-103">The `My.Applicaton.Log` and `My.Log` objects make it easy to write logging and tracing information to logs.</span></span>  
  
## <a name="how-messages-are-logged"></a><span data-ttu-id="5bc7f-104">메시지가 기록되는 방식</span><span class="sxs-lookup"><span data-stu-id="5bc7f-104">How Messages are Logged</span></span>  
 <span data-ttu-id="5bc7f-105">먼저 로그의 <xref:System.Diagnostics.TraceSource.Switch%2A> 의 <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> 속성으로 메시지의 심각도를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-105">First, the severity of the message is checked with the <xref:System.Diagnostics.TraceSource.Switch%2A> property of the log's <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> property.</span></span> <span data-ttu-id="5bc7f-106">기본적으로 심각도가 "정보" 이상인 메시지만 로그의 `TraceListener` 컬렉션에 지정된 추적 수신기로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-106">By default, only messages of severity "Information" and higher are passed on to the trace listeners, specified in the log's `TraceListener` collection.</span></span> <span data-ttu-id="5bc7f-107">그런 다음 각 수신기는 메시지의 심각도를 수신기의 <xref:System.Diagnostics.TraceSource.Switch%2A> 속성과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-107">Then, each listener compares the severity of the message to the listener's <xref:System.Diagnostics.TraceSource.Switch%2A> property.</span></span> <span data-ttu-id="5bc7f-108">메시지의 심각도가 충분히 높으면 수신기는 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-108">If the message's severity is high enough, the listener writes out the message.</span></span>  
  
 <span data-ttu-id="5bc7f-109">다음 다이어그램에서는 `WriteEntry` 메서드에 기록된 메시지가 로그의 추적 수신기의 `WriteLine` 메서드로 전달되는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-109">The following diagram shows how a message written to the `WriteEntry` method gets passed to the `WriteLine` methods of the log's trace listeners:</span></span>  
  
 <span data-ttu-id="5bc7f-110">![내 로그 호출](../../../../visual-basic/developing-apps/programming/log-info/media/mylogcall.png "MyLogCall")</span><span class="sxs-lookup"><span data-stu-id="5bc7f-110">![My Log Call](../../../../visual-basic/developing-apps/programming/log-info/media/mylogcall.png "MyLogCall")</span></span>  
  
 <span data-ttu-id="5bc7f-111">응용 프로그램의 구성 파일을 변경하여 로그 및 추적 수신기의 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-111">You can change the behavior of the log and the trace listeners by changing the application's configuration file.</span></span> <span data-ttu-id="5bc7f-112">다음 다이어그램에서는 로그의 각 부분과 구성 파일에서의 해당 위치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-112">The following diagram shows the correspondence between the parts of the log and the configuration file.</span></span>  
  
 <span data-ttu-id="5bc7f-113">![내 로그 구성](../../../../visual-basic/developing-apps/programming/log-info/media/mylogconfig.png "MyLogConfig")</span><span class="sxs-lookup"><span data-stu-id="5bc7f-113">![My Log Configuration](../../../../visual-basic/developing-apps/programming/log-info/media/mylogconfig.png "MyLogConfig")</span></span>  
  
## <a name="where-messages-are-logged"></a><span data-ttu-id="5bc7f-114">메시지가 기록되는 위치</span><span class="sxs-lookup"><span data-stu-id="5bc7f-114">Where Messages are Logged</span></span>  
 <span data-ttu-id="5bc7f-115">어셈블리에 구성 파일이 없으면 `My.Application.Log` 및 `My.Log` 개체가 <xref:System.Diagnostics.DefaultTraceListener> 클래스를 통해 응용 프로그램의 디버그 출력에 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-115">If the assembly has no configuration file, the `My.Application.Log` and `My.Log` objects write to the application's debug output (through the <xref:System.Diagnostics.DefaultTraceListener> class).</span></span> <span data-ttu-id="5bc7f-116">또한 `My.Application.Log` 개체는 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 클래스를 통해 어셈블리의 로그 파일에 기록하고, `My.Log` 개체는 <xref:System.Web.WebPageTraceListener> 클래스를 통해 ASP.NET 웹 페이지의 출력에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-116">In addition, the `My.Application.Log` object writes to the assembly's log file (through the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class), while the `My.Log` object writes to the ASP.NET Web page's output (through the <xref:System.Web.WebPageTraceListener> class).</span></span>  
  
 <span data-ttu-id="5bc7f-117">디버그 출력은 디버그 모드에서 응용 프로그램을 실행할 때 Visual Studio **출력** 창에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-117">The debug output can be viewed in the Visual Studio **Output** window when running your application in debug mode.</span></span> <span data-ttu-id="5bc7f-118">**출력** 창을 열려면 **디버그** 메뉴 항목을 클릭하고 **창**을 가리킨 다음 **출력**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-118">To open the **Output** window, click the **Debug** menu item, point to **Windows**, and then click **Output**.</span></span> <span data-ttu-id="5bc7f-119">**출력** 창의 **다음에서 출력 보기** 상자에서 **디버그** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-119">In the **Output** window, select **Debug** from the **Show output from** box.</span></span>  
  
 <span data-ttu-id="5bc7f-120">기본적으로 `My.Application.Log` 는 사용자의 응용 프로그램 데이터가 있는 경로에 로그 파일을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-120">By default, `My.Application.Log` writes the log file in the path for the user's application data.</span></span> <span data-ttu-id="5bc7f-121">경로는 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> 개체의 <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> 속성에서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-121">You can get the path from the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> property of the <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> object.</span></span> <span data-ttu-id="5bc7f-122">해당 경로의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-122">The format of that path is as follows:</span></span>  
  
 `BasePath`\\`CompanyName`\\`ProductName`\\`ProductVersion`  
  
 <span data-ttu-id="5bc7f-123">`BasePath` 의 일반적인 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-123">A typical value for `BasePath` is as follows.</span></span>  
  
 <span data-ttu-id="5bc7f-124">C:\Documents and Settings\\`username`\Application Data</span><span class="sxs-lookup"><span data-stu-id="5bc7f-124">C:\Documents and Settings\\`username`\Application Data</span></span>  
  
 <span data-ttu-id="5bc7f-125">`CompanyName`, `ProductName`및 `ProductVersion` 값은 응용 프로그램의 어셈블리 정보에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-125">The values of `CompanyName`, `ProductName`, and `ProductVersion` come from the application's assembly information.</span></span> <span data-ttu-id="5bc7f-126">로그 파일 이름의 형식은 *AssemblyName*.log이며 여기서 *AssemblyName* 은 확장명을 제외한 어셈블리의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-126">The form of the log file name is *AssemblyName*.log, where *AssemblyName* is the file name of the assembly without the extension.</span></span> <span data-ttu-id="5bc7f-127">응용 프로그램에서 로그에 쓰려고 할 때 원본 로그를 사용할 수 없는 경우와 같이 둘 이상의 로그 파일이 필요한 경우 로그 파일 이름의 형식은 *AssemblyName*-*iteration*.log이며 여기서 `iteration` 은 양의 `Integer`을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-127">If more than one log file is needed, such as when the original log is unavailable when the application attempts to write to the log, the form for the log file name is *AssemblyName*-*iteration*.log, where `iteration` is a positive `Integer`.</span></span>  
  
 <span data-ttu-id="5bc7f-128">컴퓨터 및 응용 프로그램의 구성 파일을 추가하거나 변경하여 기본 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-128">You can override the default behavior by adding or changing the computer's and the application's configuration files.</span></span> <span data-ttu-id="5bc7f-129">자세한 내용은 [Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-129">For more information, see [Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md).</span></span>  
  
## <a name="configuring-log-settings"></a><span data-ttu-id="5bc7f-130">로그 설정 구성</span><span class="sxs-lookup"><span data-stu-id="5bc7f-130">Configuring Log Settings</span></span>  
 <span data-ttu-id="5bc7f-131">`Log` 개체에는 응용 프로그램 구성 파일인 app.config 없이 작동하는 기본 구현이 있습니다. 기본값을 변경하려면 새 설정이 지정된 구성 파일을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-131">The `Log` object has a default implementation that works without an application configuration file, app.config. To change the defaults, you must add a configuration file with the new settings.</span></span> <span data-ttu-id="5bc7f-132">자세한 내용은 [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-132">For more information, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="5bc7f-133">로그 구성 섹션은 app.config 파일의 주 `<system.diagnostics>` 노드에 있는 `<configuration>` 노드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-133">The log configuration sections are located in the `<system.diagnostics>` node in the main `<configuration>` node of the app.config file.</span></span> <span data-ttu-id="5bc7f-134">로그 정보는 다음과 같은 여러 노드에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-134">Log information is defined in several nodes:</span></span>  
  
-   <span data-ttu-id="5bc7f-135">`Log` 개체의 수신기는 DefaultSource라는 이름의 `<sources>` 노드에서 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-135">The listeners for the `Log` object are defined in the `<sources>` node named DefaultSource.</span></span>  
  
-   <span data-ttu-id="5bc7f-136">`Log` 개체의 심각도 필터는 DefaultSwitch라는 이름의 `<switches>` 노드에서 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-136">The severity filter for the `Log` object is defined in the `<switches>` node named DefaultSwitch.</span></span>  
  
-   <span data-ttu-id="5bc7f-137">로그 수신기는 `<sharedListeners>` 노드에서 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-137">The log listeners are defined in the `<sharedListeners>` node.</span></span>  
  
 <span data-ttu-id="5bc7f-138">다음 코드에서 `<sources>`, `<switches>`및 `<sharedListeners>` 노드의 예제를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-138">Examples of `<sources>`, `<switches>`, and `<sharedListeners>` nodes are shown in the following code:</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="DefaultSource" switchName="DefaultSwitch">  
        <listeners>  
          <add name="FileLog"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="DefaultSwitch" value="Information" />  
    </switches>  
    <sharedListeners>  
      <add name="FileLog"  
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,  
          Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,   
          PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL"  
        initializeData="FileLogWriter"  
      />  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="changing-log-settings-after-deployment"></a><span data-ttu-id="5bc7f-139">배포 후 로그 설정 변경</span><span class="sxs-lookup"><span data-stu-id="5bc7f-139">Changing Log Settings after Deployment</span></span>  
 <span data-ttu-id="5bc7f-140">위의 예제에서 볼 수 있는 것처럼 응용 프로그램을 개발할 때 구성 설정은 app.config 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-140">When you develop an application, its configuration settings are stored in the app.config file, as shown in the examples above.</span></span> <span data-ttu-id="5bc7f-141">응용 프로그램을 배포한 후에도 구성 파일을 편집하여 로그를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-141">After you deploy your application, you can still configure the log by editing the configuration file.</span></span> <span data-ttu-id="5bc7f-142">Windows 기반 응용 프로그램에서 이 파일의 이름은 *applicationName*.exe.config이며 실행 파일과 같은 폴더에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-142">In a Windows-based application, this file's name is *applicationName*.exe.config, and it must reside in the same folder as the executable file.</span></span> <span data-ttu-id="5bc7f-143">웹 응용 프로그램의 경우 프로젝트와 연결된 Web.config 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-143">For a Web application, this is the Web.config file associated with the project.</span></span>  
  
 <span data-ttu-id="5bc7f-144">응용 프로그램은 클래스의 인스턴스를 만드는 코드를 처음으로 실행할 때 개체에 대한 정보가 있는지 구성 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-144">When your application executes the code that creates an instance of a class for the first time, it checks the configuration file for information about the object.</span></span> <span data-ttu-id="5bc7f-145">`Log` 개체의 경우에는 `Log` 개체에 처음 액세스할 때 이 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-145">For the `Log` object, this happens the first time the `Log` object is accessed.</span></span> <span data-ttu-id="5bc7f-146">시스템은 응용 프로그램이 개체를 처음으로 만들 때 단 한 번만 특정 개체에 대해 구성 파일을 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-146">The system examines the configuration file only once for any particular object—the first time your application creates the object.</span></span> <span data-ttu-id="5bc7f-147">따라서 변경 내용을 적용하려면 응용 프로그램을 다시 시작해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-147">Therefore, you may need to restart the application for the changes to take effect.</span></span>  
  
 <span data-ttu-id="5bc7f-148">배포된 응용 프로그램에서는 응용 프로그램을 시작하기 전에 스위치 개체를 다시 구성하여 추적 코드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-148">In a deployed application, you enable trace code by reconfiguring switch objects before your application starts.</span></span> <span data-ttu-id="5bc7f-149">일반적으로 이 경우에는 스위치 개체를 설정 및 해제하거나 추적 수준을 변경한 다음 응용 프로그램을 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-149">Typically, this involves turning the switch objects on and off or by changing the tracing levels, and then restarting your application.</span></span>  
  
## <a name="security-considerations"></a><span data-ttu-id="5bc7f-150">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="5bc7f-150">Security Considerations</span></span>  
 <span data-ttu-id="5bc7f-151">데이터를 로그에 쓸 때는 다음을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-151">Consider the following when writing data to the log:</span></span>  
  
-   <span data-ttu-id="5bc7f-152">**사용자 정보가 누출되지 않도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bc7f-152">**Avoid leaking user information.**</span></span> <span data-ttu-id="5bc7f-153">응용 프로그램에서 승인된 정보만 로그에 쓰도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-153">Ensure that your application writes only approved information to the log.</span></span> <span data-ttu-id="5bc7f-154">예를 들어 응용 프로그램 로그에 사용자 이름은 포함되어도 되지만 사용자 암호는 포함되지 않도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-154">For example, it may be acceptable for the application log to contain user names, but not user passwords.</span></span>  
  
-   <span data-ttu-id="5bc7f-155">**로그 위치의 보안을 강화합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bc7f-155">**Make log locations secure.**</span></span> <span data-ttu-id="5bc7f-156">잠재적으로 중요한 정보를 포함하는 모든 로그는 안전한 위치에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-156">Any log that contains potentially sensitive information should be stored in a secure location.</span></span>  
  
-   <span data-ttu-id="5bc7f-157">**잘못된 정보를 사용하지 않도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bc7f-157">**Avoid misleading information.**</span></span> <span data-ttu-id="5bc7f-158">일반적으로 응용 프로그램에서는 사용자가 입력한 데이터를 사용하기 전에 이들 데이터의 유효성을 검증해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-158">In general, your application should validate all data entered by a user before using that data.</span></span> <span data-ttu-id="5bc7f-159">여기에는 응용 프로그램 로그에 데이터를 쓰는 작업도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-159">This includes writing data to the application log.</span></span>  
  
-   <span data-ttu-id="5bc7f-160">**서비스 거부가 발생하지 않도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bc7f-160">**Avoid denial of service.**</span></span> <span data-ttu-id="5bc7f-161">응용 프로그램에서 로그에 너무 많은 정보를 쓰면 로그가 가득 차거나 중요한 정보를 찾기가 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7f-161">If your application writes too much information to the log, it could fill the log or make finding important information difficult.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc7f-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bc7f-162">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 [<span data-ttu-id="5bc7f-163">응용 프로그램의 정보 기록</span><span class="sxs-lookup"><span data-stu-id="5bc7f-163">Logging Information from the Application</span></span>](../../../../visual-basic/developing-apps/programming/log-info/logging-information-from-the-application.md)
