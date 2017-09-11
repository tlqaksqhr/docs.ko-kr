---
title: "방법: Visual Basic에서 레지스트리 키 값 읽기"
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
- registry keys, determining if a value exists in
- My.Computer.Registry object, examples
- registry, determining if values exist
- registry keys, reading from
- registry, reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: 31
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
ms.openlocfilehash: 69b833777629cfd642ab75ac055b96b59c1da70b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a><span data-ttu-id="ea3b1-102">방법: Visual Basic에서 레지스트리 키 값 읽기</span><span class="sxs-lookup"><span data-stu-id="ea3b1-102">How to: Read a Value from a Registry Key in Visual Basic</span></span>
<span data-ttu-id="ea3b1-103">`My.Computer.Registry` 개체의 `GetValue` 메서드를 사용하여 Windows 레지스트리의 값을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-103">The `GetValue` method of the `My.Computer.Registry` object can be used to read values in the Windows registry.</span></span>  
  
 <span data-ttu-id="ea3b1-104">다음 예제의 "Software\MyApp" 키가 없으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-104">If the key, "Software\MyApp" in the following example, does not exist, an exception is thrown.</span></span> <span data-ttu-id="ea3b1-105">`ValueName`(다음 예제의 "Name")이 없으면 `Nothing`이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-105">If the `ValueName`,  "Name" in the following example, does not exist, `Nothing` is returned.</span></span>  
  
 <span data-ttu-id="ea3b1-106">`GetValue` 메서드를 사용하여 지정된 값이 특정 레지스트리 키에 있는지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-106">The `GetValue` method can also be used to determine whether a given value exists in a specific registry key.</span></span>  
  
 <span data-ttu-id="ea3b1-107">코드가 웹 응용 프로그램에서 레지스트리를 읽는 경우 현재 사용자는 웹 응용 프로그램에 구현된 인증 및 가장에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-107">When code reads the registry from a Web application, the current user is determined by the authentication and impersonation that is implemented in the Web application.</span></span>  
  
### <a name="to-read-a-value-from-a-registry-key"></a><span data-ttu-id="ea3b1-108">레지스트리 키에서 값을 읽으려면</span><span class="sxs-lookup"><span data-stu-id="ea3b1-108">To read a value from a registry key</span></span>  
  
-   <span data-ttu-id="ea3b1-109">`GetValue` 메서드를 사용하고 경로 및 이름을 지정하여 레지스트리 키에서 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-109">Use the `GetValue` method, specifying the path and name) to read a value from registry key.</span></span> <span data-ttu-id="ea3b1-110">다음 예제에서는 `HKEY_CURRENT_USER\Software\MyApp`에서 `Name` 값을 읽고 메시지 상자에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-110">The following example reads the value `Name` from `HKEY_CURRENT_USER\Software\MyApp` and displays it in a message box.</span></span>  
  
     <span data-ttu-id="ea3b1-111">[!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ea3b1-111">[!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]</span></span>  
  
 <span data-ttu-id="ea3b1-112">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-112">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="ea3b1-113">코드 조각 선택에서 **Windows 운영 체제 > 레지스트리**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-113">In the code snippet picker, it is located in **Windows Operating System > Registry**.</span></span> <span data-ttu-id="ea3b1-114">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-114">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a><span data-ttu-id="ea3b1-115">레지스트리 키에 값이 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="ea3b1-115">To determine whether a value exists in a registry key</span></span>  
  
-   <span data-ttu-id="ea3b1-116">`GetValue` 메서드를 사용하여 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-116">Use the `GetValue` method to retrieve the value.</span></span> <span data-ttu-id="ea3b1-117">다음 코드는 값이 있는지 확인하고, 값이 없는 경우 메시지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-117">The following code checks whether the value exists and returns a message if it does not.</span></span>  
  
     <span data-ttu-id="ea3b1-118">[!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ea3b1-118">[!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ea3b1-119">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ea3b1-119">Robust Programming</span></span>  
 <span data-ttu-id="ea3b1-120">레지스트리는 데이터를 저장하는 데 사용되는 최상위 또는 루트 키를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-120">The registry holds top-level, or root, keys that are used to store data.</span></span> <span data-ttu-id="ea3b1-121">예를 들어 HKEY_LOCAL_MACHINE 루트 키는 모든 사용자가 사용하는 컴퓨터 수준 설정을 저장하는 데 사용되고, HKEY_CURRENT_USER는 개별 사용자와 관련된 데이터를 저장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-121">For instance, the HKEY_LOCAL_MACHINE root key is used for storing machine-level settings used by all users, while HKEY_CURRENT_USER is used for storing data specific to an individual user.</span></span>  
  
 <span data-ttu-id="ea3b1-122">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-122">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="ea3b1-123">키의 이름이 `Nothing`인 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="ea3b1-123">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="ea3b1-124">사용자에게 레지스트리 키에서 읽을 수 있는 권한이 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="ea3b1-124">The user does not have permissions to read from registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="ea3b1-125">키 이름이 255자 제한을 초과하는 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="ea3b1-125">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ea3b1-126">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="ea3b1-126">.NET Framework Security</span></span>  
 <span data-ttu-id="ea3b1-127">이 프로세스를 실행하려면 어셈블리에 <xref:System.Security.Permissions.RegistryPermission> 클래스에서 부여한 권한 수준이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-127">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="ea3b1-128">부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-128">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="ea3b1-129">마찬가지로, 사용자에게 설정을 만들거나 쓸 수 있는 올바른 ACL이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-129">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="ea3b1-130">예를 들어 코드 액세스 보안 권한이 있는 로컬 응용 프로그램에는 운영 체제 권한이 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-130">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="ea3b1-131">자세한 내용은 [코드 액세스 보안 기본 사항](https://msdn.microsoft.com/library/33tceax8)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea3b1-131">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea3b1-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea3b1-132">See Also</span></span>  
 <span data-ttu-id="ea3b1-133"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span><span class="sxs-lookup"><span data-stu-id="ea3b1-133"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span></span>   
 <span data-ttu-id="ea3b1-134"><xref:Microsoft.Win32.RegistryHive></span><span class="sxs-lookup"><span data-stu-id="ea3b1-134"><xref:Microsoft.Win32.RegistryHive></span></span>   
 [<span data-ttu-id="ea3b1-135">레지스트리 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="ea3b1-135">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)

