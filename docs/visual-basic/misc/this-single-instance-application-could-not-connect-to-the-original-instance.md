---
title: "이 단일 인스턴스 응용 프로그램 원래 인스턴스에 연결할 수 없습니다 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 113923e7cb72d1da0a8fb289f29e9afa60dda558
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="95dc1-102">이 단일 인스턴스 응용 프로그램을 원본 인스턴스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-102">This single-instance application could not connect to the original instance</span></span>
<span data-ttu-id="95dc1-103">이 단일 인스턴스 응용 프로그램을 원본 인스턴스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-103">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="95dc1-104">이 문제가 발생할 수 있는 몇 가지 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-104">Some of the possible causes for this problem are as follows:</span></span>  
  
-   <span data-ttu-id="95dc1-105">원래 인스턴스의 응답이 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-105">The original instance stopped responding.</span></span>  
  
-   <span data-ttu-id="95dc1-106">커널 개체를 만들 수 있는 권한이 응용 프로그램에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-106">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="95dc1-107">커널 개체에 대 한 자세한 내용은 참조 [뮤텍스](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2)합니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-107">For more information about kernel objects, see [Mutexes](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2).</span></span>  
  
     <span data-ttu-id="95dc1-108">커널 개체의 기본 이름은 어셈블리의 GUID, 주 버전 번호 및 부 버전 번호를 연결하여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-108">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="95dc1-109">예를 들어 기본 이름은 `3639f15d-9547-43da-8145-60da347829915.1`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-109">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="95dc1-110">응용 프로그램을 개발할 때 이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="95dc1-110">To correct this error when developing the application</span></span>  
  
1.  <span data-ttu-id="95dc1-111">응용 프로그램이 응답하지 않는 상태로 전환되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-111">Check that the application does not go into an unresponsive state.</span></span>  
  
2.  <span data-ttu-id="95dc1-112">응용 프로그램에 커널 개체를 만들 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-112">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3.  <span data-ttu-id="95dc1-113">응용 프로그램의 원래 인스턴스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-113">Restart the original instance of the application.</span></span>  
  
4.  <span data-ttu-id="95dc1-114">컴퓨터를 다시 시작하여 원래 인스턴스 응용 프로그램에 연결하는 데 필요한 리소스를 사용 중일 수 있는 프로세스를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-114">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5.  <span data-ttu-id="95dc1-115">오류가 발생한 상황을 파악하여 Microsoft 기술 지원 서비스에 전화로 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="95dc1-115">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95dc1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95dc1-116">See Also</span></span>  
 <span data-ttu-id="95dc1-117">[NIB: 방법: 응용 프로그램 (Visual Basic)에 대 한 인스턴스 만들기 동작 지정](http://msdn.microsoft.com/en-us/48539ad8-d960-4210-beab-ee65f6c6dc6e) </span><span class="sxs-lookup"><span data-stu-id="95dc1-117">[NIB: How to: Specify Instancing Behavior for an Application (Visual Basic)](http://msdn.microsoft.com/en-us/48539ad8-d960-4210-beab-ee65f6c6dc6e) </span></span>  
<span data-ttu-id="95dc1-118"> [디버거 기본 사항](https://docs.microsoft.com/visualstudio/debugger/debugger-basics) </span><span class="sxs-lookup"><span data-stu-id="95dc1-118"> [Debugger Basics](https://docs.microsoft.com/visualstudio/debugger/debugger-basics) </span></span>  
<span data-ttu-id="95dc1-119"> [PAVEOVER 제품 지원 및 내게 필요한 옵션](http://msdn.microsoft.com/en-us/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)</span><span class="sxs-lookup"><span data-stu-id="95dc1-119"> [PAVEOVER Product Support and Accessibility](http://msdn.microsoft.com/en-us/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)</span></span>
