---
title: "어셈블리 위치"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96b3105dcd1eaf6d95269d05518e6892b42a638f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="assembly-location"></a><span data-ttu-id="13a4f-102">어셈블리 위치</span><span class="sxs-lookup"><span data-stu-id="13a4f-102">Assembly Location</span></span>
<span data-ttu-id="13a4f-103">어셈블리 위치에 따라 공용 언어 런타임이 참조 시 해당 위치를 찾을 수 있는지 여부가 결정되고 어셈블리를 다른 어셈블리와 공유할 수 있는지 여부도 결정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13a4f-103">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="13a4f-104">다음 위치에 어셈블리를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13a4f-104">You can deploy an assembly in the following locations:</span></span>  
  
-   <span data-ttu-id="13a4f-105">응용 프로그램의 디렉터리 또는 하위 디렉터리.</span><span class="sxs-lookup"><span data-stu-id="13a4f-105">The application's directory or subdirectories.</span></span>  
  
     <span data-ttu-id="13a4f-106">어셈블리를 배포할 수 있는 가장 일반적인 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="13a4f-106">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="13a4f-107">응용 프로그램 루트 디렉터리의 하위 디렉터리는 언어 또는 문화권에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13a4f-107">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="13a4f-108">어셈블리에 문화권 특성의 정보가 있으면 어셈블리는 응용 프로그램 디렉터리 아래 하위 디렉터리에 문화권 이름과 함께 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a4f-108">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>  
  
-   <span data-ttu-id="13a4f-109">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="13a4f-109">The global assembly cache.</span></span>  
  
     <span data-ttu-id="13a4f-110">공용 언어 런타임이 설치되는 모든 위치에 설치되는 컴퓨터 수준 코드 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="13a4f-110">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="13a4f-111">대부분의 경우 어셈블리를 여러 응용 프로그램과 공유하려고 하면 어셈블리를 전역 어셈블리 캐시에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a4f-111">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>  
  
-   <span data-ttu-id="13a4f-112">HTTP 서버에.</span><span class="sxs-lookup"><span data-stu-id="13a4f-112">On an HTTP server.</span></span>  
  
     <span data-ttu-id="13a4f-113">HTTP 서버에 배포되는 어셈블리에는 강력한 이름이 있어야 합니다. 응용 프로그램 구성 파일의 코드베이스 섹션에 있는 어셈블리를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="13a4f-113">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a4f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13a4f-114">See Also</span></span>  
 [<span data-ttu-id="13a4f-115">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="13a4f-115">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="13a4f-116">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="13a4f-116">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
 [<span data-ttu-id="13a4f-117">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="13a4f-117">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="13a4f-118">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="13a4f-118">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
