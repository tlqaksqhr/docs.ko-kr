---
title: "단일 인스턴스 시작에 필요한 운영 체제 리소스를 가져올 수 없기 때문에 예기치 않은 오류가 발생 했습니다 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
dev_langs:
- VB
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 03ab2d1c746fbc28c0c6f3e59371cc6bbd4050cd
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="6d9e0-102">단일 인스턴스 시작에 필요한 운영 체제 리소스를 가져올 수 없기 때문에 예기치 않은 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d9e0-102">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>
<span data-ttu-id="6d9e0-103">응용 프로그램이 필요한 운영 체제 리소스를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d9e0-103">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="6d9e0-104">이 문제가 발생할 수 있는 몇 가지 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6d9e0-104">Some of the possible causes for this problem are:</span></span>  
  
-   <span data-ttu-id="6d9e0-105">응용 프로그램에 명명된 운영 체제 개체를 만들 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d9e0-105">The application does not have permissions to create named operating-system objects.</span></span>  
  
-   <span data-ttu-id="6d9e0-106">공용 언어 런타임에 메모리 매핑된 파일을 만들 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d9e0-106">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
-   <span data-ttu-id="6d9e0-107">응용 프로그램이 운영 체제 개체에 액세스해야 하는데 다른 프로세스에서 해당 개체를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d9e0-107">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6d9e0-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="6d9e0-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="6d9e0-109">응용 프로그램에 명명된 운영 체제 개체를 만들 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6d9e0-109">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2.  <span data-ttu-id="6d9e0-110">공용 언어 런타임에 메모리 매핑된 파일을 만들 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6d9e0-110">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3.  <span data-ttu-id="6d9e0-111">컴퓨터를 다시 시작하여 원래 인스턴스 응용 프로그램에 연결하는 데 필요한 리소스를 사용 중일 수 있는 프로세스를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="6d9e0-111">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4.  <span data-ttu-id="6d9e0-112">오류가 발생한 상황을 파악하여 Microsoft 기술 지원 서비스에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="6d9e0-112">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d9e0-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d9e0-113">See Also</span></span>  
 <span data-ttu-id="6d9e0-114">[프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="6d9e0-114">[Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="6d9e0-115"> [디버거 기본 사항](https://docs.microsoft.com/visualstudio/debugger/debugger-basics) </span><span class="sxs-lookup"><span data-stu-id="6d9e0-115"> [Debugger Basics](https://docs.microsoft.com/visualstudio/debugger/debugger-basics) </span></span>  
<span data-ttu-id="6d9e0-116"> [의견 보내기](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="6d9e0-116"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
