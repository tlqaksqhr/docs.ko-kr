---
title: "방법: Windows 서비스 일시 중지(Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: d44358d3f76f50a06ede5e7d720f4f48d80893de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="32b2a-102">방법: Windows 서비스 일시 중지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32b2a-102">How to: Pause a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="32b2a-103">사용 하 여이 예제는 <xref:System.ServiceProcess.ServiceController> 구성 요소는 로컬 컴퓨터에 IIS 관리 서비스를 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32b2a-104">예제</span><span class="sxs-lookup"><span data-stu-id="32b2a-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="32b2a-105">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="32b2a-106">에 있는 코드 조각 선택에서 **Windows 운영 체제 > Windows 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="32b2a-107">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32b2a-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="32b2a-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="32b2a-108">Compiling the Code</span></span>  
 <span data-ttu-id="32b2a-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-109">This example requires:</span></span>  
  
-   <span data-ttu-id="32b2a-110">System.serviceprocess.dll에 대 한 프로젝트 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-110">A project reference to System.serviceprocess.dll.</span></span>  
  
-   <span data-ttu-id="32b2a-111"><xref:System.ServiceProcess> 네임스페이스의 멤버에 대한 액세스 권한.</span><span class="sxs-lookup"><span data-stu-id="32b2a-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="32b2a-112">코드에서 멤버 이름을 정규화하지 않는 경우 `Imports` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="32b2a-113">자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32b2a-113">For more information, see [Imports Statement (.NET Namespace and Type)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="32b2a-114">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="32b2a-114">Robust Programming</span></span>  
 <span data-ttu-id="32b2a-115"><xref:System.ServiceProcess.ServiceController.MachineName%2A> 의 속성은 <xref:System.ServiceProcess.ServiceController> 클래스는 기본적으로 로컬 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="32b2a-116">다른 컴퓨터에서 Windows 서비스를 참조 하려면 변경 된 <xref:System.ServiceProcess.ServiceController.MachineName%2A> 속성을 해당 컴퓨터의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="32b2a-117">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-117">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="32b2a-118">서비스를 일시 중지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-118">The service cannot be paused.</span></span> <span data-ttu-id="32b2a-119">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="32b2a-119">(<xref:System.InvalidOperationException>)</span></span>  
  
-   <span data-ttu-id="32b2a-120">시스템 API에 액세스할 때 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-120">An error occurred when accessing a system API.</span></span> <span data-ttu-id="32b2a-121">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="32b2a-121">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="32b2a-122">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="32b2a-122">.NET Framework Security</span></span>  
 <span data-ttu-id="32b2a-123">컴퓨터에서 서비스의 제어를 사용 하 여 제한 될 수도 있습니다는 <xref:System.ServiceProcess.ServiceControllerPermissionAccess> 사용 권한을 설정 하는 <xref:System.ServiceProcess.ServiceControllerPermission>합니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-123">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="32b2a-124">사용 하 여 서비스 정보에 대 한 액세스를 제한할 수 있습니다는 <xref:System.Security.Permissions.PermissionState> 사용 권한을 설정 하는 <xref:System.Security.Permissions.SecurityPermission>합니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-124">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b2a-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32b2a-125">See Also</span></span>  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>  
 [<span data-ttu-id="32b2a-126">방법: Windows 서비스 (Visual Basic)를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="32b2a-126">How to: Continue a Windows Service (Visual Basic)</span></span>](../../../docs/framework/windows-services/how-to-continue-a-windows-service-visual-basic.md)
