---
title: 레지스트리 읽기 및 쓰기(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
ms.openlocfilehash: 6ce05b956ebf9a544eb8c95165b0f709c694f334
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332937"
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a><span data-ttu-id="f10ce-102">레지스트리 읽기 및 쓰기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f10ce-102">Reading from and Writing to the Registry (Visual Basic)</span></span>
<span data-ttu-id="f10ce-103">이 항목에서는 레지스트리와 관련된 작업 및 개념 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ce-103">This topic describes task and conceptual topics that are associated with the registry.</span></span>  
  
 <span data-ttu-id="f10ce-104">Visual Basic에서 프로그래밍할 때 Visual Basic에서 제공하는 기능 또는 .NET Framework의 레지스트리 클래스를 사용하여 레지스트리에 액세스하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f10ce-104">When programming in Visual Basic, you can choose to access the registry by means of either the functions provided by Visual Basic or the registry classes of the .NET Framework.</span></span> <span data-ttu-id="f10ce-105">레지스트리는 운영 체제의 정보는 물론 컴퓨터에 호스트된 응용 프로그램의 정보도 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ce-105">The registry hosts information from the operating system as well as information from applications hosted on the machine.</span></span> <span data-ttu-id="f10ce-106">레지스트리로 작업하면 시스템 리소스나 보호된 정보에 부적절하게 액세스하여 보안이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f10ce-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f10ce-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f10ce-107">In This Section</span></span>  
 [<span data-ttu-id="f10ce-108">방법: 레지스트리 키 만들기 및 값 설정</span><span class="sxs-lookup"><span data-stu-id="f10ce-108">How to: Create a Registry Key and Set Its Value</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 <span data-ttu-id="f10ce-109">`My.Computer.Registry` 개체의 `CreateSubKey` 및 `SetValue` 메서드를 사용하여 레지스트리 키를 만들고 값을 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ce-109">Describes how to use the `CreateSubKey` and `SetValue` methods of the `My.Computer.Registry` object to create a registry key and set its value.</span></span>  
  
 [<span data-ttu-id="f10ce-110">방법: 레지스트리 키 값 읽기</span><span class="sxs-lookup"><span data-stu-id="f10ce-110">How to: Read a Value from a Registry Key</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 <span data-ttu-id="f10ce-111">`My.Computer.Registry` 개체의 `GetValue` 메서드를 사용하여 레지스트리 키에서 값을 읽는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ce-111">Describes how to use the `GetValue` method of the `My.Computer.Registry` object to read a value from a registry key.</span></span>  
  
 [<span data-ttu-id="f10ce-112">방법: 레지스트리 키 삭제</span><span class="sxs-lookup"><span data-stu-id="f10ce-112">How to: Delete a Registry Key</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 <span data-ttu-id="f10ce-113">`My.Computer.Registry.CurrentUser` 속성의 `DeleteSubKey` 메서드를 사용하여 레지스트리 키를 삭제하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ce-113">Describes how to use the `DeleteSubKey` method of the `My.Computer.Registry.CurrentUser` property to delete a registry key.</span></span>  
  
 [<span data-ttu-id="f10ce-114">Microsoft.Win32 네임스페이스를 사용하여 레지스트리 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="f10ce-114">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 <span data-ttu-id="f10ce-115">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]의 `Registry` 및 `RegistryKey` 클래스를 사용하여 레지스트리에 액세스하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ce-115">Describes how to use the `Registry` and `RegistryKey` classes of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to access the registry.</span></span>  
  
 [<span data-ttu-id="f10ce-116">보안 및 레지스트리</span><span class="sxs-lookup"><span data-stu-id="f10ce-116">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 <span data-ttu-id="f10ce-117">레지스트리 관련 보안 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ce-117">Discusses security issues involving the registry.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f10ce-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f10ce-118">Related Sections</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 <span data-ttu-id="f10ce-119">`My.Computer.Registry` 개체의 멤버를 나열하고 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ce-119">Lists and explains members of the `My.Computer.Registry` object.</span></span>  
  
 <xref:Microsoft.Win32.Registry>  
 <span data-ttu-id="f10ce-120">개별 키와 멤버에 대한 링크와 함께 `Registry` 클래스의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ce-120">Presents an overview of the `Registry` class, along with links to individual keys and members.</span></span>
