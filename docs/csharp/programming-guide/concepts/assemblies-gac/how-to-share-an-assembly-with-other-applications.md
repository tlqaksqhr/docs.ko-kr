---
title: "방법: 다른 응용 프로그램과 어셈블리 공유(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 85117cfdc9b12a93891e89727412a03acc83289b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a><span data-ttu-id="dddeb-102">방법: 다른 응용 프로그램과 어셈블리 공유(C#)</span><span class="sxs-lookup"><span data-stu-id="dddeb-102">How to: Share an Assembly with Other Applications (C#)</span></span>
<span data-ttu-id="dddeb-103">어셈블리는 전용이거나 공유될 수 있습니다. 기본적으로 대부분의 간단한 프로그램은 다른 응용 프로그램에서 사용되지 않으므로 전용 어셈블리로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dddeb-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="dddeb-104">다른 응용 프로그램과 어셈블리를 공유하려면 GAC([전역 어셈블리 캐시](../../../../framework/app-domains/gac.md))에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dddeb-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="dddeb-105">어셈블리 공유</span><span class="sxs-lookup"><span data-stu-id="dddeb-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="dddeb-106">어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dddeb-106">Create your assembly.</span></span> <span data-ttu-id="dddeb-107">자세한 내용은 [어셈블리 만들기](../../../../framework/app-domains/create-assemblies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dddeb-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="dddeb-108">어셈블리에 강력한 이름을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="dddeb-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="dddeb-109">자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dddeb-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="dddeb-110">어셈블리에 버전 정보를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="dddeb-110">Assign version information to your assembly.</span></span> <span data-ttu-id="dddeb-111">자세한 내용은 [어셈블리 버전 관리](https://msdn.microsoft.com/library/51ket42z)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dddeb-111">For more information, see [Assembly Versioning](https://msdn.microsoft.com/library/51ket42z).</span></span>  
  
4.  <span data-ttu-id="dddeb-112">전역 어셈블리 캐시에 어셈블리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dddeb-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="dddeb-113">자세한 내용은 [방법: 전역 어셈블리 캐시에 어셈블리 설치](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dddeb-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="dddeb-114">다른 응용 프로그램에서 어셈블리에 포함된 형식에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="dddeb-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="dddeb-115">자세한 내용은 [방법: 강력한 이름의 어셈블리 참조](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dddeb-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dddeb-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dddeb-116">See Also</span></span>  
 <span data-ttu-id="dddeb-117">[C# 프로그래밍 가이드](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="dddeb-117">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="dddeb-118">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="dddeb-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)

