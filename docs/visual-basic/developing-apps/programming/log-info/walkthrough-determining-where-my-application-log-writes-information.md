---
title: "My.Application.Log가 정보를 기록하는 위치 확인(Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Log object, output location
- output, application log location
- My.Application.Log object, outpout location
- event logs, determining output location
- application event logs, output location
- applications [Visual Basic], output location
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 36c91f607a5a9d0dcf65ee6e049b9a49cdd37929
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-determining-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="ca95d-102">연습: My.Application.Log가 정보를 기록하는 위치 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca95d-102">Walkthrough: Determining Where My.Application.Log Writes Information (Visual Basic)</span></span>
<span data-ttu-id="ca95d-103">`My.Application.Log` 개체는 여러 로그 수신기에 정보를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-103">The `My.Application.Log` object can write information to several log listeners.</span></span> <span data-ttu-id="ca95d-104">로그 수신기는 컴퓨터의 구성 파일로 구성되며 응용 프로그램의 구성 파일로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-104">The log listeners are configured by the computer's configuration file and can be overridden by an application's configuration file.</span></span> <span data-ttu-id="ca95d-105">이 항목에서는 기본 설정과 응용 프로그램의 설정을 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-105">This topic describes the default settings and how to determine the settings for your application.</span></span>  
  
 <span data-ttu-id="ca95d-106">기본 출력 위치에 대한 자세한 내용은 [응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca95d-106">For more information about the default output locations, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
### <a name="to-determine-the-listeners-for-myapplicationlog"></a><span data-ttu-id="ca95d-107">My.Application.Log의 수신기를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="ca95d-107">To determine the listeners for My.Application.Log</span></span>  
  
1.  <span data-ttu-id="ca95d-108">어셈블리의 구성 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-108">Locate the assembly's configuration file.</span></span> <span data-ttu-id="ca95d-109">어셈블리를 개발하는 경우 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 솔루션 탐색기 **에서**의 app.config에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-109">If you are developing the assembly, you can access the app.config in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] from the **Solution Explorer**.</span></span> <span data-ttu-id="ca95d-110">그렇지 않은 경우 구성 파일 이름은 어셈블리의 이름에 ".config"가 붙은 형태이며 어셈블리와 같은 디렉터리에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-110">Otherwise, the configuration file name is the assembly's name appended with ".config", and it is located in the same directory as the assembly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca95d-111">구성 파일에 없는 어셈블리도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-111">Not every assembly has a configuration file.</span></span>  
  
     <span data-ttu-id="ca95d-112">구성 파일은 XML 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-112">The configuration file is an XML file.</span></span>  
  
2.  <span data-ttu-id="ca95d-113">`<listeners>` 특성이 "DefaultSource"인 `<source>` 섹션에서 `name` 섹션에 있는 `<sources>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-113">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="ca95d-114">`<sources>` 섹션은 최상위 `<system.diagnostics>` 섹션의 `<configuration>` 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-114">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
     <span data-ttu-id="ca95d-115">이들 섹션이 없으면 컴퓨터의 구성 파일이 `My.Application.Log` 로그 수신기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-115">If these sections do not exist, then the computer's configuration file may configure the `My.Application.Log` log listeners.</span></span> <span data-ttu-id="ca95d-116">다음 단계에서는 컴퓨터 구성 파일에 정의된 내용을 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-116">The following steps describe how to determine what the computer configuration file defines:</span></span>  
  
    1.  <span data-ttu-id="ca95d-117">컴퓨터의 machine.config 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-117">Locate the computer's machine.config file.</span></span> <span data-ttu-id="ca95d-118">이 파일은 일반적으로 *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* 디렉터리에 있으며, 여기서 `SystemRoot` 는 운영 체제 디렉터리이고 `frameworkVersion` 은 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-118">Typically, it is located in the *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* directory, where `SystemRoot` is the operating system directory, and `frameworkVersion` is the version of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
         <span data-ttu-id="ca95d-119">machine.config의 설정은 응용 프로그램의 구성 파일로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-119">The settings in machine.config can be overridden by an application's configuration file.</span></span>  
  
         <span data-ttu-id="ca95d-120">아래 나열된 선택적 요소가 없을 경우 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-120">If the optional elements listed below do not exist, you can create them.</span></span>  
  
    2.  <span data-ttu-id="ca95d-121">최상위 `<listeners>` 섹션의 `<source>` 섹션에 있는 `name` 섹션에서 `<sources>` 특성이 "DefaultSource"인 `<system.diagnostics>` 섹션에 있는 `<configuration>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-121">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
         <span data-ttu-id="ca95d-122">이들 섹션이 없으면 `My.Application.Log` 에 기본 로그 수신기만 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-122">If these sections do not exist, then the `My.Application.Log` has only the default log listeners.</span></span>  
  
3.  <span data-ttu-id="ca95d-123"><`listeners>` 섹션에서 <`add>` 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-123">Locate the <`add>` elements in the <`listeners>` section.</span></span>  
  
     <span data-ttu-id="ca95d-124">이들 요소는 명명된 로그 수신기를 `My.Application.Log` 소스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-124">These elements add the named log listeners to `My.Application.Log` source.</span></span>  
  
4.  <span data-ttu-id="ca95d-125">최상위 `<add>` 섹션에 있는 `<sharedListeners>` 섹션의 `<system.diagnostics>` 섹션에서 로그 수신기의 이름이 지정된 `<configuration>` 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-125">Locate the `<add>` elements with the names of the log listeners in the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="ca95d-126">여러 형식의 공유 수신기의 경우, 수신기의 초기화 데이터에는 수신기가 데이터를 보낼 위치에 대한 설명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-126">For many types of shared listeners, the listener's initialization data includes a description of where the listener directs the data:</span></span>  
  
    -   <span data-ttu-id="ca95d-127">소개에서 설명한 것처럼 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName> 수신기는 파일 로그에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-127">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName> listener writes to a file log, as described in the introduction.</span></span>  
  
    -   <span data-ttu-id="ca95d-128"><xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName> 수신기는 `initializeData` 매개 변수로 지정된 컴퓨터 이벤트 로그에 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-128">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName> listener writes information to the computer event log specified by the `initializeData` parameter.</span></span> <span data-ttu-id="ca95d-129">이벤트 로그를 보려면 **서버 탐색기** 또는 **Windows 이벤트 뷰어**를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-129">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="ca95d-130">자세한 내용은 [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca95d-130">For more information, see [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299).</span></span>  
  
    -   <span data-ttu-id="ca95d-131"><xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName> 및 <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName> 수신기는 `initializeData` 매개 변수에 지정된 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-131">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName> listeners write to the file specified in the `initializeData` parameter.</span></span>  
  
    -   <span data-ttu-id="ca95d-132"><xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName> 수신기는 명령줄 콘솔에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ca95d-132">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName> listener writes to the command-line console.</span></span>  
  
    -   <span data-ttu-id="ca95d-133">다른 형식의 로그 수신기가 정보를 쓰는 위치에 대한 자세한 내용은 해당 형식의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca95d-133">For information about where other types of log listeners write information, consult that type's documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca95d-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca95d-134">See Also</span></span>  
 <span data-ttu-id="ca95d-135"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ca95d-135"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="ca95d-136"><xref:System.Diagnostics.DefaultTraceListener></span><span class="sxs-lookup"><span data-stu-id="ca95d-136"><xref:System.Diagnostics.DefaultTraceListener></span></span>   
 <span data-ttu-id="ca95d-137"><xref:System.Diagnostics.EventLogTraceListener></span><span class="sxs-lookup"><span data-stu-id="ca95d-137"><xref:System.Diagnostics.EventLogTraceListener></span></span>   
 <span data-ttu-id="ca95d-138"><xref:System.Diagnostics.DelimitedListTraceListener></span><span class="sxs-lookup"><span data-stu-id="ca95d-138"><xref:System.Diagnostics.DelimitedListTraceListener></span></span>   
 <span data-ttu-id="ca95d-139"><xref:System.Diagnostics.XmlWriterTraceListener></span><span class="sxs-lookup"><span data-stu-id="ca95d-139"><xref:System.Diagnostics.XmlWriterTraceListener></span></span>   
 <span data-ttu-id="ca95d-140"><xref:System.Diagnostics.ConsoleTraceListener></span><span class="sxs-lookup"><span data-stu-id="ca95d-140"><xref:System.Diagnostics.ConsoleTraceListener></span></span>   
 <span data-ttu-id="ca95d-141"><xref:System.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="ca95d-141"><xref:System.Diagnostics></span></span>   
 <span data-ttu-id="ca95d-142">[응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="ca95d-142">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="ca95d-143">[방법: 예외 기록](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="ca95d-143">[How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span></span>  
 <span data-ttu-id="ca95d-144">[방법: 로그 메시지 쓰기](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ca95d-144">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 <span data-ttu-id="ca95d-145">[연습: My.Application.Log가 정보를 기록하는 위치 변경](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="ca95d-145">[Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span></span>  
 <span data-ttu-id="ca95d-146">[.NET Framework의 ETW 이벤트](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299) </span><span class="sxs-lookup"><span data-stu-id="ca95d-146">[ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299) </span></span>  
 [<span data-ttu-id="ca95d-147">문제 해결: 로그 수신기</span><span class="sxs-lookup"><span data-stu-id="ca95d-147">Troubleshooting: Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)

