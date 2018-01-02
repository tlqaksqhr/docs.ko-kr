---
title: "알고리즘 이름을 암호화 클래스에 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 9c9c5b1f69200d4ee5d39c98445b668813718dd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="4ff25-102">알고리즘 이름을 암호화 클래스에 매핑</span><span class="sxs-lookup"><span data-stu-id="4ff25-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="4ff25-103">다음과 같이 네 가지 개발자 사용 하 여 암호화 개체를 만들 수는 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4ff25-103">There are four ways a developer can create a cryptography object using the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span></span>  
  
-   <span data-ttu-id="4ff25-104">사용 하 여 개체를 만들는 **새** 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-104">Create an object by using the **new** operator.</span></span>  
  
-   <span data-ttu-id="4ff25-105">호출 하 여 특정 암호화 알고리즘을 구현 하는 개체 만들기는 **만들기** 해당 알고리즘에 대 한 추상 클래스에 메서드.</span><span class="sxs-lookup"><span data-stu-id="4ff25-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
-   <span data-ttu-id="4ff25-106">호출 하 여 특정 암호화 알고리즘을 구현 하는 개체 만들기는 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="4ff25-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="4ff25-107">호출 하 여 암호화 알고리즘 (예: 블록 대칭 암호화)의 클래스를 구현 하는 개체를 만들기는 **만들기** 해당 유형의 알고리즘에 대 한 추상 클래스에 메서드 (같은 <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span><span class="sxs-lookup"><span data-stu-id="4ff25-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="4ff25-108">예를 들어 개발자가 바이트 집합의 SHA1 해시를 계산 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="4ff25-109"><xref:System.Security.Cryptography> 네임 스페이스에는 SHA1 알고리즘, 관리 되는 순수 하 게 구현 하는 하나 및 CryptoAPI를 래핑하는 하나 두 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="4ff25-110">개발자는 인스턴스화할 특정 SHA1 구현 하도록 선택할 수 (같은 <xref:System.Security.Cryptography.SHA1Managed>)를 호출 하 여는 **새** 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="4ff25-111">그러나 공용 언어 런타임 클래스를 구현 하는 SHA1 해시 알고리즘을 로드 하는 클래스에 중요 하지 않으면 경우 개발자 개체를 만들 수를 호출 하 여는 <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="4ff25-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4ff25-112">이 메서드를 호출 **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, SHA1 해시 알고리즘의 구현을 반환 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="4ff25-113">개발자를 호출할 수도 **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** 하므로 암호화 구성을 기본적으로.NET Framework에서 제공 하는 알고리즘에 대 한 짧은 이름이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="4ff25-114">개발자를 호출할 수 있는 해시 알고리즘을 사용 하는 중요 하지 않습니다는 <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> 해싱 변환을 구현 하는 개체를 반환 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="4ff25-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="4ff25-115">구성 파일에 알고리즘 이름 매핑</span><span class="sxs-lookup"><span data-stu-id="4ff25-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="4ff25-116">기본적으로 런타임은 반환는 <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> 모든 4 가지 시나리오에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="4ff25-117">그러나 컴퓨터 관리자에는 마지막 두 시나리오에서 메서드를 반환 하는 개체의 유형을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="4ff25-118">이 위해 컴퓨터 구성 파일 (Machine.config)에서 사용 하려면 클래스에 알고리즘 이름을 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="4ff25-119">고 런타임을 구성 하는 방법을 보여 주는 다음 예제를 **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, 및  **System.Security.Cryptography.HashAlgorithm.Create** 반환는 `MySHA1HashClass` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="4ff25-120">특성의 이름을 지정할 수 있습니다는 [< cryptoClass\> 요소](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (이전 예제에서는 특성의 이름을 `MySHA1Hash`).</span><span class="sxs-lookup"><span data-stu-id="4ff25-120">You can specify the name of the attribute in the [<cryptoClass\> element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="4ff25-121">특성의 값은  **\<cryptoClass >** 요소는 공용 언어 런타임에서 클래스를 찾기 위해 사용 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="4ff25-122">에 지정 된 요구 사항을 충족 하는 모든 문자열을 사용할 수 있습니다 [정규화 된 형식 이름 지정](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="4ff25-123">동일한 클래스에 여러 알고리즘 이름을 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="4ff25-124">[ \<r y > 요소](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 는 클래스에 한 개의 알고리즘 이름을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-124">The [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="4ff25-125">**이름** 특성은 호출할 때 사용 되는 문자열로 수는 **System.Security.Cryptography.CryptoConfig.CreateFromName** 메서드 또는 클래스는 추상 암호화는 의이름<xref:System.Security.Cryptography> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="4ff25-126">값은 **클래스** 특성은 특성의 이름에서  **\<cryptoClass >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ff25-127">SHA1 알고리즘을 호출 하 여 가져올 수 있습니다는 <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> 또는 **Security.CryptoConfig.CreateFromName("SHA1")** 메서드.</span><span class="sxs-lookup"><span data-stu-id="4ff25-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="4ff25-128">각 메서드는 SHA1 알고리즘을 구현 하는 개체를 반환 하는지만 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="4ff25-129">각 알고리즘의 이름 구성 파일에서 같은 클래스에 매핑할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="4ff25-130">기본 이름 및 매핑되는 클래스의 목록에 대 한 참조 <xref:System.Security.Cryptography.CryptoConfig>합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff25-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ff25-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ff25-131">See Also</span></span>  
 [<span data-ttu-id="4ff25-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="4ff25-132">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="4ff25-133">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="4ff25-133">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
