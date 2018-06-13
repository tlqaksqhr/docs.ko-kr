---
title: 암호화 클래스 구성
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b12d5d95a17439308d79d094e8c22206778f3128
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743253"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="496fc-102">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="496fc-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="496fc-103">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 컴퓨터 관리자는 기본 암호화 알고리즘 및.NET Framework와 적절 하 게 작성된 된 응용 프로그램에서 사용 하는 알고리즘 구현의 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="496fc-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="496fc-104">예를 들어 암호화 알고리즘의 자체 구현을 보유 정확해 구현에 구현에서 제공 하는 대신 기본은 [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="496fc-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span> <span data-ttu-id="496fc-105">암호화를 사용 하는 관리 되는 응용 프로그램에 특정 구현에 바인딩하려면 명시적으로 선택할 수, 있지만 암호화 구성 시스템을 사용 하 여 암호화 개체를 생성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="496fc-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="496fc-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="496fc-106">In This Section</span></span>  
 [<span data-ttu-id="496fc-107">알고리즘 이름을 암호화 클래스에 매핑</span><span class="sxs-lookup"><span data-stu-id="496fc-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="496fc-108">암호화 클래스에 알고리즘 이름을 매핑하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="496fc-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="496fc-109">개체 식별자를 암호화 알고리즘에 매핑</span><span class="sxs-lookup"><span data-stu-id="496fc-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="496fc-110">암호화 알고리즘에 개체 식별자를 매핑하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="496fc-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="496fc-111">관련 단원</span><span class="sxs-lookup"><span data-stu-id="496fc-111">Related Sections</span></span>  
 [<span data-ttu-id="496fc-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="496fc-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="496fc-113">제공 하는 암호화 서비스의 개요를 제공는 [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="496fc-113">Provides an overview of cryptographic services provided by the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span>  
  
 [<span data-ttu-id="496fc-114">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="496fc-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="496fc-115">암호화 알고리즘을 구현하는 클래스에 편리한 알고리즘 이름을 매핑하는 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="496fc-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
