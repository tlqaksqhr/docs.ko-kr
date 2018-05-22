---
title: 사용자 지정 로그 수신기 만들기(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
ms.openlocfilehash: 6139a1fef2b2c37bc2c8a6167febd060d8d01fb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a><span data-ttu-id="31d7c-102">연습: 사용자 지정 로그 수신기 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31d7c-102">Walkthrough: Creating Custom Log Listeners (Visual Basic)</span></span>
<span data-ttu-id="31d7c-103">이 연습에서는 사용자 지정 로그 수신기를 만들고 `My.Application.Log` 개체의 출력을 수신 대기하도록 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-103">This walkthrough demonstrates how to create a custom log listener and configure it to listen to the output of the `My.Application.Log` object.</span></span>  
  
## <a name="getting-started"></a><span data-ttu-id="31d7c-104">시작</span><span class="sxs-lookup"><span data-stu-id="31d7c-104">Getting Started</span></span>  
 <span data-ttu-id="31d7c-105">로그 수신기는 <xref:System.Diagnostics.TraceListener> 클래스에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-105">Log listeners must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
#### <a name="to-create-the-listener"></a><span data-ttu-id="31d7c-106">수신기를 만들려면</span><span class="sxs-lookup"><span data-stu-id="31d7c-106">To create the listener</span></span>  
  
-   <span data-ttu-id="31d7c-107"><xref:System.Diagnostics.TraceListener>에서 상속하는 이름이 `SimpleListener`인 클래스를 응용 프로그램에서 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-107">In your application, create a class named `SimpleListener` that inherits from <xref:System.Diagnostics.TraceListener>.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_1.vb)]  
  
     <span data-ttu-id="31d7c-108">기본 클래스에 필요한 <xref:System.Diagnostics.TraceListener.Write%2A> 및 <xref:System.Diagnostics.TraceListener.WriteLine%2A> 메서드는 `MsgBox`를 호출하여 해당 입력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-108">The <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods, required by the base class, call `MsgBox` to display their input.</span></span>  
  
     <span data-ttu-id="31d7c-109"><xref:System.Diagnostics.TraceListener.Write%2A> 및 <xref:System.Diagnostics.TraceListener.WriteLine%2A> 메서드의 특정이 기본 클래스 메서드와 일치하도록 이 두 메서드에 <xref:System.Security.Permissions.HostProtectionAttribute> 특성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-109">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is applied to the <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods so that their attributes match the base class methods.</span></span> <span data-ttu-id="31d7c-110"><xref:System.Security.Permissions.HostProtectionAttribute> 특성을 사용하면 코드를 실행하는 호스트에서는 코드가 호스트 보호 동기화를 노출하는지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-110">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute allows the host that runs the code to determine that the code exposes host-protection synchronization.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31d7c-111"><xref:System.Security.Permissions.HostProtectionAttribute> 특성은 공용 언어 런타임을 호스트하고 SQL Server와 같은 호스트 보호를 구현하는 관리되지 않는 응용 프로그램에서만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-111">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is effective only on unmanaged applications that host the common language runtime and that implement host protection, such as SQL Server.</span></span>  
  
 <span data-ttu-id="31d7c-112">`My.Application.Log`가 로그 수신기를 사용하도록 하려면 로그 수신기를 포함하는 어셈블리에 강력한 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-112">To ensure that `My.Application.Log` uses your log listener, you should strongly name the assembly that contains your log listener.</span></span>  
  
 <span data-ttu-id="31d7c-113">다음 절차에서는 강력한 이름의 로그 수신기 어셈블리를 만들기 위한 몇 가지 간단한 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-113">The next procedure provides some simple steps for creating a strongly named log-listener assembly.</span></span> <span data-ttu-id="31d7c-114">자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31d7c-114">For more information, see [Creating and Using Strong-Named Assemblies](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md).</span></span>  
  
#### <a name="to-strongly-name-the-log-listener-assembly"></a><span data-ttu-id="31d7c-115">로그 수신기 어셈블리에 강력한 이름을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="31d7c-115">To strongly name the log-listener assembly</span></span>  
  
1.  <span data-ttu-id="31d7c-116">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="31d7c-117">**프로젝트** 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-117">On the **Project** menu, choose **Properties**.</span></span>   
  
2.  <span data-ttu-id="31d7c-118">**시그니처** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-118">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="31d7c-119">**어셈블리 시그니처** 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-119">Select the **Sign the assembly** box.</span></span>  
  
4.  <span data-ttu-id="31d7c-120">**강력한 이름 키 파일 선택** 드롭다운 목록에서 **\<새로 만들기>** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-120">Select **\<New>** from the **Choose a strong name key file** drop-down list.</span></span>  
  
     <span data-ttu-id="31d7c-121">**강력한 이름 키 만들기** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-121">The **Create Strong Name Key** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="31d7c-122">**키 파일 이름** 상자에 키 파일의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-122">Provide a name for the key file in the **Key file name** box.</span></span>  
  
6.  <span data-ttu-id="31d7c-123">**암호 입력** 및 **암호 확인** 상자에 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-123">Enter a password in the **Enter password** and **Confirm password** boxes.</span></span>  
  
7.  <span data-ttu-id="31d7c-124">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-124">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="31d7c-125">응용 프로그램을 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-125">Rebuild the application.</span></span>  
  
## <a name="adding-the-listener"></a><span data-ttu-id="31d7c-126">수신기 추가</span><span class="sxs-lookup"><span data-stu-id="31d7c-126">Adding the Listener</span></span>  
 <span data-ttu-id="31d7c-127">이제 어셈블리에 강력한 이름을 지정했으므로 `My.Application.Log`에서 로그 수신기를 사용하도록 수신기의 강력한 이름을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-127">Now that the assembly has a strong name, you need to determine the strong name of the listener so that `My.Application.Log` uses your log listener.</span></span>  
  
 <span data-ttu-id="31d7c-128">강력한 이름의 형식은 다음과 같은 구문을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-128">The format of a strongly named type is as follows.</span></span>  
  
 <span data-ttu-id="31d7c-129">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span><span class="sxs-lookup"><span data-stu-id="31d7c-129">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span></span>  
  
#### <a name="to-determine-the-strong-name-of-the-listener"></a><span data-ttu-id="31d7c-130">수신기의 강력한 이름을 결정하려면</span><span class="sxs-lookup"><span data-stu-id="31d7c-130">To determine the strong name of the listener</span></span>  
  
-   <span data-ttu-id="31d7c-131">다음 코드에서는 `SimpleListener`에 대해 강력한 형식의 이름을 결정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-131">The following code shows how to determine the strongly named type name for `SimpleListener`.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_2.vb)]  
  
     <span data-ttu-id="31d7c-132">강력한 형식의 이름은 프로젝트에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-132">The strong name of the type depends on your project.</span></span>  
  
 <span data-ttu-id="31d7c-133">강력한 이름을 사용하면 수신기를 `My.Application.Log` 로그 수신기 컬렉션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-133">With the strong name, you can add the listener to the `My.Application.Log` log-listener collection.</span></span>  
  
#### <a name="to-add-the-listener-to-myapplicationlog"></a><span data-ttu-id="31d7c-134">My.Application.Log에 수신기를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="31d7c-134">To add the listener to My.Application.Log</span></span>  
  
1.  <span data-ttu-id="31d7c-135">**솔루션 탐색기**에서 app.config를 마우스 오른쪽 단추로 클릭하고 **열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-135">Right-click on app.config in the **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="31d7c-136">또는</span><span class="sxs-lookup"><span data-stu-id="31d7c-136">-or-</span></span>  
  
     <span data-ttu-id="31d7c-137">app.config 파일이 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="31d7c-137">If there is an app.config file:</span></span>  
  
    1.  <span data-ttu-id="31d7c-138">**프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-138">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="31d7c-139">**새 항목 추가** 대화 상자에서 **응용 프로그램 구성 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-139">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="31d7c-140">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-140">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="31d7c-141">`<listeners>` 특성이 "DefaultSource"인 `<source>` 섹션에서 `name` 섹션에 있는 `<sources>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-141">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="31d7c-142">`<sources>` 섹션은 최상위 `<system.diagnostics>` 섹션의 `<configuration>` 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-142">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="31d7c-143">이 요소를 `<listeners>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-143">Add this element to the `<listeners>` section:</span></span>  
  
    ```xml  
    <add name="SimpleLog" />  
    ```  
  
4.  <span data-ttu-id="31d7c-144">최상위 `<sharedListeners>` 섹션의 `<system.diagnostics>` 섹션에서 `<configuration>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-144">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="31d7c-145">다음 요소를 `<sharedListeners>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-145">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     <span data-ttu-id="31d7c-146">수신기의 강력한 이름이 되도록 `SimpleLogStrongName`의 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="31d7c-146">Change the value of `SimpleLogStrongName` to be the strong name of the listener.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d7c-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31d7c-147">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 [<span data-ttu-id="31d7c-148">응용 프로그램 로그 작업</span><span class="sxs-lookup"><span data-stu-id="31d7c-148">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [<span data-ttu-id="31d7c-149">방법: 예외 기록</span><span class="sxs-lookup"><span data-stu-id="31d7c-149">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)  
 [<span data-ttu-id="31d7c-150">방법: 로그 메시지 쓰기</span><span class="sxs-lookup"><span data-stu-id="31d7c-150">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)  
 [<span data-ttu-id="31d7c-151">연습: My.Application.Log가 정보를 기록하는 위치 변경</span><span class="sxs-lookup"><span data-stu-id="31d7c-151">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
