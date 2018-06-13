---
title: My.Application, My.Computer 및 My.User를 사용한 작업 수행(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: bc2b0521598c00cdb398d936d61d65874a9cf274
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583398"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="458ff-102">My.Application, My.Computer 및 My.User를 사용한 작업 수행(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="458ff-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>
<span data-ttu-id="458ff-103">세 개의 핵심 `My` 액세스 정보 및 일반적으로 사용 되는 기능을 제공 하는 개체는 `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), 및 `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span><span class="sxs-lookup"><span data-stu-id="458ff-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="458ff-104">현재 응용 프로그램, 응용 프로그램은 설치 하는 컴퓨터 또는 응용 프로그램의 현재 사용자와 관련 된 정보를 각각 액세스할 수 이러한 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="458ff-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="458ff-105">My.Application, My.Computer 및 My.User</span><span class="sxs-lookup"><span data-stu-id="458ff-105">My.Application, My.Computer, and My.User</span></span>  
 <span data-ttu-id="458ff-106">다음 예에서는 정보 수 있는 방법을 보여 줍니다. 사용 하 여 검색할 `My`합니다.</span><span class="sxs-lookup"><span data-stu-id="458ff-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 <span data-ttu-id="458ff-107">정보를 검색 하는 것 외에도 이러한 세 가지 개체를 통해 노출 되는 멤버 수 있습니다 해당 개체와 관련 된 메서드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="458ff-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="458ff-108">예를 들어, 다양 한 파일을 조작 하거나 통해 레지스트리를 업데이트할 방법 액세스할 수 있습니다 `My.Computer`합니다.</span><span class="sxs-lookup"><span data-stu-id="458ff-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="458ff-109">파일 I/O가 훨씬 쉽고 빠르게 `My`, 다양 한 파일, 디렉터리 및 드라이브를 조작 하기 위한 메서드와 속성을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="458ff-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="458ff-110"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser> 개체 고정 폭 필드 또는 구분 큰 구조화 된 파일에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="458ff-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="458ff-111">이 예제는 `TextFieldParser``reader` 에서 읽기를 사용 하 여 `C:\TestFolder1\test1.txt`합니다.</span><span class="sxs-lookup"><span data-stu-id="458ff-111">This example opens the `TextFieldParser``reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 <span data-ttu-id="458ff-112">`My.Application` 응용 프로그램에 대 한 문화권을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="458ff-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="458ff-113">다음 예제에서는이 메서드를 호출 수 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="458ff-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="458ff-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="458ff-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [<span data-ttu-id="458ff-115">My가 프로젝트 형식에 의존하는 방식</span><span class="sxs-lookup"><span data-stu-id="458ff-115">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
