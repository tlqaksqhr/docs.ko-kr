---
title: "방법: Visual Basic에서 레지스트리 키 삭제"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.DeleteSetting
dev_langs:
- VB
helpviewer_keywords:
- GetSetting function
- registry, deleting values
- GetAllSettings function
- registry keys, deleting
- registry, deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: 28
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
ms.openlocfilehash: 0fc37aff9f6a0ae3a7953377ebf95179d01bb693
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a><span data-ttu-id="74c0a-102">방법: Visual Basic에서 레지스트리 키 삭제</span><span class="sxs-lookup"><span data-stu-id="74c0a-102">How to: Delete a Registry Key in Visual Basic</span></span>
<span data-ttu-id="74c0a-103"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> 및 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> 메서드를 사용하여 레지스트리 키를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74c0a-103">The <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> and <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> methods can be used to delete registry keys.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="74c0a-104">프로시저</span><span class="sxs-lookup"><span data-stu-id="74c0a-104">Procedure</span></span>  
  
#### <a name="to-delete-a-registry-key"></a><span data-ttu-id="74c0a-105">레지스트리 키를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="74c0a-105">To delete a registry key</span></span>  
  
-   <span data-ttu-id="74c0a-106">`DeleteSubKey` 메서드를 사용하여 레지스트리 키를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="74c0a-106">Use the `DeleteSubKey` method to delete a registry key.</span></span> <span data-ttu-id="74c0a-107">이 예제에서는 CurrentUser 하이브에서 Software/TestApp 키를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="74c0a-107">This example deletes the key Software/TestApp in the CurrentUser hive.</span></span> <span data-ttu-id="74c0a-108">코드에서 이 키를 적절한 문자열로 변경하거나 사용자가 제공한 정보를 사용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74c0a-108">You can change this in the code to the appropriate string, or have it rely on user-supplied information.</span></span>  
  
     <span data-ttu-id="74c0a-109">[!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="74c0a-109">[!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="74c0a-110">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="74c0a-110">Robust Programming</span></span>  
 <span data-ttu-id="74c0a-111">키/값 쌍이 존재하지 않는 경우 `DeleteSubKey` 메서드는 빈 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="74c0a-111">The `DeleteSubKey` method returns an empty string if the key/value pair does not exist.</span></span>  
  
 <span data-ttu-id="74c0a-112">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="74c0a-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="74c0a-113">키의 이름이 `Nothing`인 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="74c0a-113">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="74c0a-114">사용자에게 레지스트리 키를 삭제할 수 있는 권한이 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="74c0a-114">The user does not have permissions to delete registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="74c0a-115">키 이름이 255자 제한을 초과하는 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="74c0a-115">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="74c0a-116">레지스트리 키가 읽기 전용인 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="74c0a-116">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="74c0a-117">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="74c0a-117">.NET Framework Security</span></span>  
 <span data-ttu-id="74c0a-118">충분한 런타임 권한이 부여되지 않았거나(<xref:System.Security.Permissions.RegistryPermission>) 사용자에게 설정을 만들거나 쓰기 위한 올바른 액세스 권한(ACL에 따라 결정됨)이 없는 경우 레지스트리 호출에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="74c0a-118">Registry calls fail if either sufficient run-time permissions are not granted (<xref:System.Security.Permissions.RegistryPermission>) or if the user does not have the correct access (as determined by the ACLs) for creating or writing to settings.</span></span> <span data-ttu-id="74c0a-119">예를 들어 코드 액세스 보안 권한이 있는 로컬 응용 프로그램에는 운영 체제 권한이 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74c0a-119">For example, a local application that has the code access security permission might not have operating system permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c0a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74c0a-120">See Also</span></span>  
 <span data-ttu-id="74c0a-121"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span><span class="sxs-lookup"><span data-stu-id="74c0a-121"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span></span>   
 <span data-ttu-id="74c0a-122"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span><span class="sxs-lookup"><span data-stu-id="74c0a-122"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span></span>   
 <span data-ttu-id="74c0a-123"><xref:Microsoft.Win32.RegistryKey></span><span class="sxs-lookup"><span data-stu-id="74c0a-123"><xref:Microsoft.Win32.RegistryKey></span></span>   
 <span data-ttu-id="74c0a-124">[보안 및 레지스트리](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="74c0a-124">[Security and the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md) </span></span>  
 [<span data-ttu-id="74c0a-125">레지스트리 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="74c0a-125">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)

