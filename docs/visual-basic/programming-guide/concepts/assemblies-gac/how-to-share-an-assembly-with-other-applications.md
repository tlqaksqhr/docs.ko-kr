---
title: "방법: 다른 응용 프로그램 (Visual Basic) 프로그램과 어셈블리 공유 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ceebb3934c269284db18c9ca8e561417eaf5baa1
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="37a6f-102">방법: 다른 응용 프로그램 (Visual Basic) 프로그램과 어셈블리 공유</span><span class="sxs-lookup"><span data-stu-id="37a6f-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="37a6f-103">어셈블리 전용 또는 공유 될 수 있습니다: 기본적으로 대부분의 간단한 프로그램으로 구성 전용 어셈블리의 하므로 다른 응용 프로그램에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37a6f-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="37a6f-104">다른 응용 프로그램과 어셈블리를 공유할 수 있도록 배치 해야에 [전역 어셈블리 캐시](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) (GAC)입니다.</span><span class="sxs-lookup"><span data-stu-id="37a6f-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="37a6f-105">어셈블리 공유</span><span class="sxs-lookup"><span data-stu-id="37a6f-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="37a6f-106">어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="37a6f-106">Create your assembly.</span></span> <span data-ttu-id="37a6f-107">자세한 내용은 참조 [어셈블리 만들기](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4)합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6f-107">For more information, see [Creating Assemblies](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4).</span></span>  
  
2.  <span data-ttu-id="37a6f-108">어셈블리에 강력한 이름을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6f-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="37a6f-109">자세한 내용은 참조 [하는 방법: 강력한 이름으로 어셈블리 서명](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67)합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6f-109">For more information, see [How to: Sign an Assembly with a Strong Name](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67).</span></span>  
  
3.  <span data-ttu-id="37a6f-110">어셈블리에 버전 정보를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6f-110">Assign version information to your assembly.</span></span> <span data-ttu-id="37a6f-111">자세한 내용은 참조 [어셈블리 버전 관리](https://msdn.microsoft.com/library/51ket42z)합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6f-111">For more information, see [Assembly Versioning](https://msdn.microsoft.com/library/51ket42z).</span></span>  
  
4.  <span data-ttu-id="37a6f-112">전역 어셈블리 캐시에 어셈블리를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6f-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="37a6f-113">자세한 내용은 참조 [하는 방법: 전역 어셈블리 캐시에 어셈블리 설치](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743)합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6f-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743).</span></span>  
  
5.  <span data-ttu-id="37a6f-114">다른 응용 프로그램에서 어셈블리에 포함 된 형식에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6f-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="37a6f-115">자세한 내용은 참조 [하는 방법: 강력한 이름의 어셈블리를 참조](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813)합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6f-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37a6f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37a6f-116">See Also</span></span>  
 <span data-ttu-id="37a6f-117">[프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)
 [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="37a6f-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)
 [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="37a6f-118"> [어셈블리를 사용한 프로그래밍](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)</span><span class="sxs-lookup"><span data-stu-id="37a6f-118"> [Programming with Assemblies](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)</span></span>
