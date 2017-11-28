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
ms.openlocfilehash: e069c1636004896bfb193fd70a352195ba045865
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-location"></a><span data-ttu-id="8bbfd-102">어셈블리 위치</span><span class="sxs-lookup"><span data-stu-id="8bbfd-102">Assembly Location</span></span>
<span data-ttu-id="8bbfd-103">어셈블리 위치에 따라 공용 언어 런타임이 참조 시 해당 위치를 찾을 수 있는지 여부가 결정되고 어셈블리를 다른 어셈블리와 공유할 수 있는지 여부도 결정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbfd-103">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="8bbfd-104">다음 위치에 어셈블리를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbfd-104">You can deploy an assembly in the following locations:</span></span>  
  
-   <span data-ttu-id="8bbfd-105">응용 프로그램의 디렉터리 또는 하위 디렉터리.</span><span class="sxs-lookup"><span data-stu-id="8bbfd-105">The application's directory or subdirectories.</span></span>  
  
     <span data-ttu-id="8bbfd-106">어셈블리를 배포할 수 있는 가장 일반적인 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbfd-106">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="8bbfd-107">응용 프로그램 루트 디렉터리의 하위 디렉터리는 언어 또는 문화권에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbfd-107">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="8bbfd-108">어셈블리에 문화권 특성의 정보가 있으면 어셈블리는 응용 프로그램 디렉터리 아래 하위 디렉터리에 문화권 이름과 함께 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbfd-108">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>  
  
-   <span data-ttu-id="8bbfd-109">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="8bbfd-109">The global assembly cache.</span></span>  
  
     <span data-ttu-id="8bbfd-110">공용 언어 런타임이 설치되는 모든 위치에 설치되는 컴퓨터 수준 코드 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbfd-110">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="8bbfd-111">대부분의 경우 어셈블리를 여러 응용 프로그램과 공유하려고 하면 어셈블리를 전역 어셈블리 캐시에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbfd-111">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>  
  
-   <span data-ttu-id="8bbfd-112">HTTP 서버에.</span><span class="sxs-lookup"><span data-stu-id="8bbfd-112">On an HTTP server.</span></span>  
  
     <span data-ttu-id="8bbfd-113">HTTP 서버에 배포되는 어셈블리에는 강력한 이름이 있어야 합니다. 응용 프로그램 구성 파일의 코드베이스 섹션에 있는 어셈블리를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="8bbfd-113">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bbfd-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bbfd-114">See Also</span></span>  
 [<span data-ttu-id="8bbfd-115">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="8bbfd-115">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="8bbfd-116">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="8bbfd-116">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
 [<span data-ttu-id="8bbfd-117">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="8bbfd-117">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="8bbfd-118">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="8bbfd-118">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
