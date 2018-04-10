---
title: 시작 설정 스키마
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
caps.latest.revision: 10
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: f344139fd7d7c84aa75ab5e17b6312f3b0c3e031
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="startup-settings-schema"></a><span data-ttu-id="73e38-102">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="73e38-102">Startup Settings Schema</span></span>
<span data-ttu-id="73e38-103">시작 설정은 응용 프로그램을 실행해야 하는 공용 언어 런타임의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73e38-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="73e38-104">요소</span><span class="sxs-lookup"><span data-stu-id="73e38-104">Element</span></span>|<span data-ttu-id="73e38-105">설명</span><span class="sxs-lookup"><span data-stu-id="73e38-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73e38-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="73e38-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="73e38-107">응용 프로그램에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73e38-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="73e38-108">런타임 버전 1.1로 빌드된 응용 프로그램은 **\<supportedRuntime>** 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e38-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="73e38-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="73e38-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="73e38-110">응용 프로그램이 지원하는 공용 언어 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73e38-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="73e38-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="73e38-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="73e38-112">**\<requiredRuntime>** 및 **\<supportedRuntime>** 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e38-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73e38-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73e38-113">See Also</span></span>  
 [<span data-ttu-id="73e38-114">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="73e38-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="73e38-115">\<PaveOver> 사용할 런타임 버전 지정</span><span class="sxs-lookup"><span data-stu-id="73e38-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
