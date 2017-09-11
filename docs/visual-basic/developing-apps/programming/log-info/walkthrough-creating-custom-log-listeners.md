---
title: "사용자 지정 로그 수신기 만들기(Visual Basic)"
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
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bc6fde8dcbb27157f3fd180ad393bb406222195e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a><span data-ttu-id="05a7a-102">연습: 사용자 지정 로그 수신기 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05a7a-102">Walkthrough: Creating Custom Log Listeners (Visual Basic)</span></span>
<span data-ttu-id="05a7a-103">이 연습에서는 사용자 지정 로그 수신기를 만들고 `My.Application.Log` 개체의 출력을 수신 대기하도록 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-103">This walkthrough demonstrates how to create a custom log listener and configure it to listen to the output of the `My.Application.Log` object.</span></span>  
  
## <a name="getting-started"></a><span data-ttu-id="05a7a-104">시작</span><span class="sxs-lookup"><span data-stu-id="05a7a-104">Getting Started</span></span>  
 <span data-ttu-id="05a7a-105">로그 수신기는 <xref:System.Diagnostics.TraceListener> 클래스에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-105">Log listeners must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
#### <a name="to-create-the-listener"></a><span data-ttu-id="05a7a-106">수신기를 만들려면</span><span class="sxs-lookup"><span data-stu-id="05a7a-106">To create the listener</span></span>  
  
-   <span data-ttu-id="05a7a-107"><xref:System.Diagnostics.TraceListener>에서 상속하는 이름이 `SimpleListener`인 클래스를 응용 프로그램에서 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-107">In your application, create a class named `SimpleListener` that inherits from <xref:System.Diagnostics.TraceListener>.</span></span>  
  
     <span data-ttu-id="05a7a-108">[!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="05a7a-108">[!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_1.vb)]</span></span>  
  
     <span data-ttu-id="05a7a-109">기본 클래스에 필요한 <xref:System.Diagnostics.TraceListener.Write%2A> 및 <xref:System.Diagnostics.TraceListener.WriteLine%2A> 메서드는 `MsgBox`를 호출하여 해당 입력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-109">The <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods, required by the base class, call `MsgBox` to display their input.</span></span>  
  
     <span data-ttu-id="05a7a-110"><xref:System.Diagnostics.TraceListener.Write%2A> 및 <xref:System.Diagnostics.TraceListener.WriteLine%2A> 메서드의 특정이 기본 클래스 메서드와 일치하도록 이 두 메서드에 <xref:System.Security.Permissions.HostProtectionAttribute> 특성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-110">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is applied to the <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods so that their attributes match the base class methods.</span></span> <span data-ttu-id="05a7a-111"><xref:System.Security.Permissions.HostProtectionAttribute> 특성을 사용하면 코드를 실행하는 호스트에서는 코드가 호스트 보호 동기화를 노출하는지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-111">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute allows the host that runs the code to determine that the code exposes host-protection synchronization.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05a7a-112"><xref:System.Security.Permissions.HostProtectionAttribute> 특성은 공용 언어 런타임을 호스트하고 SQL Server와 같은 호스트 보호를 구현하는 관리되지 않는 응용 프로그램에서만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-112">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is effective only on unmanaged applications that host the common language runtime and that implement host protection, such as SQL Server.</span></span>  
  
 <span data-ttu-id="05a7a-113">`My.Application.Log`가 로그 수신기를 사용하도록 하려면 로그 수신기를 포함하는 어셈블리에 강력한 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-113">To ensure that `My.Application.Log` uses your log listener, you should strongly name the assembly that contains your log listener.</span></span>  
  
 <span data-ttu-id="05a7a-114">다음 절차에서는 강력한 이름의 로그 수신기 어셈블리를 만들기 위한 몇 가지 간단한 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-114">The next procedure provides some simple steps for creating a strongly named log-listener assembly.</span></span> <span data-ttu-id="05a7a-115">자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](https://msdn.microsoft.com/library/xwb8f617)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05a7a-115">For more information, see [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617).</span></span>  
  
#### <a name="to-strongly-name-the-log-listener-assembly"></a><span data-ttu-id="05a7a-116">로그 수신기 어셈블리에 강력한 이름을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="05a7a-116">To strongly name the log-listener assembly</span></span>  
  
1.  <span data-ttu-id="05a7a-117">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-117">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="05a7a-118">**프로젝트** 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-118">On the **Project** menu, choose **Properties**.</span></span> <span data-ttu-id="05a7a-119">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05a7a-119">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="05a7a-120">**시그니처** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-120">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="05a7a-121">**어셈블리 시그니처** 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-121">Select the **Sign the assembly** box.</span></span>  
  
4.  <span data-ttu-id="05a7a-122">**강력한 이름 키 파일 선택** 드롭다운 목록에서 **\<새로 만들기>**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-122">Select **\<New>** from the **Choose a strong name key file** drop-down list.</span></span>  
  
     <span data-ttu-id="05a7a-123">**강력한 이름 키 만들기** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-123">The **Create Strong Name Key** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="05a7a-124">**키 파일 이름** 상자에 키 파일의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-124">Provide a name for the key file in the **Key file name** box.</span></span>  
  
6.  <span data-ttu-id="05a7a-125">**암호 입력** 및 **암호 확인** 상자에 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-125">Enter a password in the **Enter password** and **Confirm password** boxes.</span></span>  
  
7.  <span data-ttu-id="05a7a-126">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-126">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="05a7a-127">응용 프로그램을 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-127">Rebuild the application.</span></span>  
  
## <a name="adding-the-listener"></a><span data-ttu-id="05a7a-128">수신기 추가</span><span class="sxs-lookup"><span data-stu-id="05a7a-128">Adding the Listener</span></span>  
 <span data-ttu-id="05a7a-129">이제 어셈블리에 강력한 이름을 지정했으므로 `My.Application.Log`에서 로그 수신기를 사용하도록 수신기의 강력한 이름을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-129">Now that the assembly has a strong name, you need to determine the strong name of the listener so that `My.Application.Log` uses your log listener.</span></span>  
  
 <span data-ttu-id="05a7a-130">강력한 이름의 형식은 다음과 같은 구문을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-130">The format of a strongly named type is as follows.</span></span>  
  
 <span data-ttu-id="05a7a-131">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span><span class="sxs-lookup"><span data-stu-id="05a7a-131">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span></span>  
  
#### <a name="to-determine-the-strong-name-of-the-listener"></a><span data-ttu-id="05a7a-132">수신기의 강력한 이름을 결정하려면</span><span class="sxs-lookup"><span data-stu-id="05a7a-132">To determine the strong name of the listener</span></span>  
  
-   <span data-ttu-id="05a7a-133">다음 코드에서는 `SimpleListener`에 대해 강력한 형식의 이름을 결정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-133">The following code shows how to determine the strongly named type name for `SimpleListener`.</span></span>  
  
     <span data-ttu-id="05a7a-134">[!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="05a7a-134">[!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_2.vb)]</span></span>  
  
     <span data-ttu-id="05a7a-135">강력한 형식의 이름은 프로젝트에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-135">The strong name of the type depends on your project.</span></span>  
  
 <span data-ttu-id="05a7a-136">강력한 이름을 사용하면 수신기를 `My.Application.Log` 로그 수신기 컬렉션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-136">With the strong name, you can add the listener to the `My.Application.Log` log-listener collection.</span></span>  
  
#### <a name="to-add-the-listener-to-myapplicationlog"></a><span data-ttu-id="05a7a-137">My.Application.Log에 수신기를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="05a7a-137">To add the listener to My.Application.Log</span></span>  
  
1.  <span data-ttu-id="05a7a-138">**솔루션 탐색기**에서 app.config를 마우스 오른쪽 단추로 클릭하고 **열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-138">Right-click on app.config in the **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="05a7a-139">또는</span><span class="sxs-lookup"><span data-stu-id="05a7a-139">-or-</span></span>  
  
     <span data-ttu-id="05a7a-140">app.config 파일이 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="05a7a-140">If there is an app.config file:</span></span>  
  
    1.  <span data-ttu-id="05a7a-141">**프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-141">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="05a7a-142">**새 항목 추가** 대화 상자에서 **응용 프로그램 구성 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-142">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="05a7a-143">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-143">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="05a7a-144">`<listeners>` 특성이 "DefaultSource"인 `<source>` 섹션에서 `name` 섹션에 있는 `<sources>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-144">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="05a7a-145">`<sources>` 섹션은 최상위 `<system.diagnostics>` 섹션의 `<configuration>` 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-145">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="05a7a-146">이 요소를 `<listeners>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-146">Add this element to the `<listeners>` section:</span></span>  
  
    ```xml  
    <add name="SimpleLog" />  
    ```  
  
4.  <span data-ttu-id="05a7a-147">최상위 `<sharedListeners>` 섹션의 `<system.diagnostics>` 섹션에서 `<configuration>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-147">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="05a7a-148">다음 요소를 `<sharedListeners>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-148">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     <span data-ttu-id="05a7a-149">수신기의 강력한 이름이 되도록 `SimpleLogStrongName`의 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="05a7a-149">Change the value of `SimpleLogStrongName` to be the strong name of the listener.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05a7a-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05a7a-150">See Also</span></span>  
 <span data-ttu-id="05a7a-151"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="05a7a-151"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="05a7a-152">[응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="05a7a-152">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="05a7a-153">[방법: 예외 기록](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="05a7a-153">[How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span></span>  
 <span data-ttu-id="05a7a-154">[방법: 로그 메시지 쓰기](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="05a7a-154">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 [<span data-ttu-id="05a7a-155">연습: My.Application.Log가 정보를 기록하는 위치 변경</span><span class="sxs-lookup"><span data-stu-id="05a7a-155">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)

