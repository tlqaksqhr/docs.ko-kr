---
title: "방법: 파일 작업에 대한 진행률 대화 상자 제공(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: a43fb764e6a1ba0a2f1ad1645624c9d8a55bc858
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="d09b5-102">방법: 파일 작업에 대한 진행률 대화 상자 제공(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d09b5-102">How to: Provide a Progress Dialog Box for File Operations (C# Programming Guide)</span></span>
<span data-ttu-id="d09b5-103"><xref:Microsoft.VisualBasic?displayProperty=fullName> 네임스페이스의 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> 메서드를 사용하는 경우 Windows에서 파일 작업 진행률을 보여 주는 표준 대화 상자를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d09b5-103">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=fullName> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="d09b5-104">Visual Studio에서 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="d09b5-104">To add a reference in Visual Studio</span></span>  
  
1.  <span data-ttu-id="d09b5-105">메뉴 모음에서 **프로젝트**, **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d09b5-105">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="d09b5-106">**참조 관리자** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d09b5-106">The **Reference Manager** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="d09b5-107">**어셈블리** 영역에서 **프레임워크**가 선택되지 않은 경우 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d09b5-107">In the **Assemblies** area, choose**Framework** if it isn’t already chosen.</span></span>  
  
3.  <span data-ttu-id="d09b5-108">이름 목록에서 **Microsoft.VisualBasic** 확인란을 선택한 다음 **확인** 단추를 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="d09b5-108">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d09b5-109">예제</span><span class="sxs-lookup"><span data-stu-id="d09b5-109">Example</span></span>  
 <span data-ttu-id="d09b5-110">다음 코드는 `sourcePath`로 지정된 디렉터리를 `destinationPath`로 지정된 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d09b5-110">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="d09b5-111">또한 이 코드는 작업이 완료되기까지 남은 예상 시간을 보여 주는 표준 대화 상자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d09b5-111">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 <span data-ttu-id="d09b5-112">[!code-cs[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d09b5-112">[!code-cs[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d09b5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d09b5-113">See Also</span></span>  
 [<span data-ttu-id="d09b5-114">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d09b5-114">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

