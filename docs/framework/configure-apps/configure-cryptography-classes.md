---
title: "암호화 클래스 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 79eb9f9ef95dae24dd38fa93b137c9303815143b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="8a526-102">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="8a526-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="8a526-103">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 컴퓨터 관리자는 기본 암호화 알고리즘 및.NET Framework와 적절 하 게 작성된 된 응용 프로그램에서 사용 하는 알고리즘 구현의 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a526-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="8a526-104">예를 들어 암호화 알고리즘의 자체 구현을 보유 정확해 구현에 구현에서 제공 하는 대신 기본은 [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="8a526-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span> <span data-ttu-id="8a526-105">암호화를 사용 하는 관리 되는 응용 프로그램에 특정 구현에 바인딩하려면 명시적으로 선택할 수, 있지만 암호화 구성 시스템을 사용 하 여 암호화 개체를 생성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a526-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a526-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="8a526-106">In This Section</span></span>  
 [<span data-ttu-id="8a526-107">알고리즘 이름을 암호화 클래스에 매핑</span><span class="sxs-lookup"><span data-stu-id="8a526-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="8a526-108">암호화 클래스에 알고리즘 이름을 매핑하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a526-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="8a526-109">개체 식별자를 암호화 알고리즘에 매핑</span><span class="sxs-lookup"><span data-stu-id="8a526-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="8a526-110">암호화 알고리즘에 개체 식별자를 매핑하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a526-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8a526-111">관련 단원</span><span class="sxs-lookup"><span data-stu-id="8a526-111">Related Sections</span></span>  
 [<span data-ttu-id="8a526-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="8a526-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="8a526-113">제공 하는 암호화 서비스의 개요를 제공는 [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="8a526-113">Provides an overview of cryptographic services provided by the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span>  
  
 [<span data-ttu-id="8a526-114">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8a526-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="8a526-115">암호화 알고리즘을 구현하는 클래스에 편리한 알고리즘 이름을 매핑하는 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8a526-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
