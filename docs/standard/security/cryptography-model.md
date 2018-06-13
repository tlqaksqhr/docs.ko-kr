---
title: .NET Framework 암호화 모델
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- cryptography [.NET Framework], model
- encryption [.NET Framework], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ced7ed2cb8d3ae3bb24211c6e7dafd1744fb9559
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587458"
---
# <a name="net-framework-cryptography-model"></a><span data-ttu-id="4d985-102">.NET Framework 암호화 모델</span><span class="sxs-lookup"><span data-stu-id="4d985-102">.NET Framework Cryptography Model</span></span>
<span data-ttu-id="4d985-103">.NET Framework에서는 많은 표준 암호화 알고리즘의 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-103">The .NET Framework provides implementations of many standard cryptographic algorithms.</span></span> <span data-ttu-id="4d985-104">이러한 알고리즘은 사용하기 쉽고 가능한 가장 안전한 기본 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-104">These algorithms are easy to use and have the safest possible default properties.</span></span> <span data-ttu-id="4d985-105">또한 개체 상속, 스트림 디자인 및 구성의 .NET Framework 암호화 모델은 크게 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-105">In addition, the .NET Framework cryptography model of object inheritance, stream design, and configuration is extremely extensible.</span></span>  
  
## <a name="object-inheritance"></a><span data-ttu-id="4d985-106">개체 상속</span><span class="sxs-lookup"><span data-stu-id="4d985-106">Object Inheritance</span></span>  
 <span data-ttu-id="4d985-107">.NET Framework 보안 시스템은 파생 클래스 상속의 확장 가능한 패턴을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-107">The .NET Framework security system implements an extensible pattern of derived class inheritance.</span></span> <span data-ttu-id="4d985-108">계층 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-108">The hierarchy is as follows:</span></span>  
  
-   <span data-ttu-id="4d985-109"><xref:System.Security.Cryptography.SymmetricAlgorithm>, <xref:System.Security.Cryptography.AsymmetricAlgorithm> 또는 <xref:System.Security.Cryptography.HashAlgorithm>과 같은 알고리즘 형식 클래스.</span><span class="sxs-lookup"><span data-stu-id="4d985-109">Algorithm type class, such as <xref:System.Security.Cryptography.SymmetricAlgorithm>,  <xref:System.Security.Cryptography.AsymmetricAlgorithm> or <xref:System.Security.Cryptography.HashAlgorithm>.</span></span> <span data-ttu-id="4d985-110">이 수준은 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-110">This level is abstract.</span></span>  
  
-   <span data-ttu-id="4d985-111">알고리즘 형식 클래스에서 상속되는 알고리즘 클래스. 예를 들어 <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RC2> 또는 <xref:System.Security.Cryptography.ECDiffieHellman>입니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-111">Algorithm class that inherits from an algorithm type class; for example, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RC2>, or <xref:System.Security.Cryptography.ECDiffieHellman>.</span></span> <span data-ttu-id="4d985-112">이 수준은 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-112">This level is abstract.</span></span>  
  
-   <span data-ttu-id="4d985-113">알고리즘 클래스에서 상속되는 알고리즘 클래스의 구현. 예를 들어 <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> 또는 <xref:System.Security.Cryptography.ECDiffieHellmanCng>입니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-113">Implementation of an algorithm class that inherits from an algorithm class; for example, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider>, or <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="4d985-114">이 수준은 완전히 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-114">This level is fully implemented.</span></span>  
  
 <span data-ttu-id="4d985-115">이 패턴의 파생 클래스를 사용하면 새로운 알고리즘 또는 기존 알고리즘의 새 구현을 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-115">Using this pattern of derived classes, it is easy to add a new algorithm or a new implementation of an existing algorithm.</span></span> <span data-ttu-id="4d985-116">예를 들어 새로운 공용 키 알고리즘을 만들려면 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 클래스에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-116">For example, to create a new public-key algorithm, you would inherit from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class.</span></span> <span data-ttu-id="4d985-117">특정 알고리즘의 새 구현을 만들려면 해당 알고리즘의 비추상 파생 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-117">To create a new implementation of a specific algorithm, you would create a non-abstract derived class of that algorithm.</span></span>  
  
## <a name="how-algorithms-are-implemented-in-the-net-framework"></a><span data-ttu-id="4d985-118">.NET Framework에서 알고리즘이 구현되는 방식</span><span class="sxs-lookup"><span data-stu-id="4d985-118">How Algorithms Are Implemented in the .NET Framework</span></span>  
 <span data-ttu-id="4d985-119">알고리즘에 사용할 수 있는 다양한 구현의 예로 대칭 알고리즘을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="4d985-119">As an example of the different implementations available for an algorithm, consider symmetric algorithms.</span></span> <span data-ttu-id="4d985-120">모든 대칭 알고리즘의 기본은 <xref:System.Security.Cryptography.SymmetricAlgorithm>으로, 다음 알고리즘에 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-120">The base for all symmetric algorithms is <xref:System.Security.Cryptography.SymmetricAlgorithm>, which is inherited by the following algorithms:</span></span>  
  
1.  <xref:System.Security.Cryptography.Aes>  
  
2.  <xref:System.Security.Cryptography.DES>  
  
3.  <xref:System.Security.Cryptography.RC2>  
  
4.  <xref:System.Security.Cryptography.Rijndael>  
  
5.  <xref:System.Security.Cryptography.TripleDES>  
  
 <span data-ttu-id="4d985-121"><xref:System.Security.Cryptography.Aes>는 두 클래스 <xref:System.Security.Cryptography.AesCryptoServiceProvider> 및 <xref:System.Security.Cryptography.AesManaged>에 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-121"><xref:System.Security.Cryptography.Aes> is inherited by two classes: <xref:System.Security.Cryptography.AesCryptoServiceProvider> and <xref:System.Security.Cryptography.AesManaged>.</span></span> <span data-ttu-id="4d985-122"><xref:System.Security.Cryptography.AesCryptoServiceProvider> 클래스는 Aes의 Windows CAPI(암호화 API) 구현에 대한 래퍼인 반면, <xref:System.Security.Cryptography.AesManaged> 클래스는 완전히 관리 코드로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-122">The <xref:System.Security.Cryptography.AesCryptoServiceProvider> class is a wrapper around the Windows Cryptography API (CAPI) implementation of Aes, whereas the <xref:System.Security.Cryptography.AesManaged> class is written entirely in managed code.</span></span> <span data-ttu-id="4d985-123">관리되는 구현 및 CAPI 구현 외에도 세 번째 유형의 구현인 CNG(Cryptography Next Generation)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-123">There is also a third type of implementation, Cryptography Next Generation (CNG), in addition to the managed and CAPI implementations.</span></span> <span data-ttu-id="4d985-124">CNG 알고리즘의 한 예는 <xref:System.Security.Cryptography.ECDiffieHellmanCng>입니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-124">An example of a CNG algorithm is <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="4d985-125">CNG 알고리즘은 Windows Vista 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-125">CNG algorithms are available on Windows Vista and later.</span></span>  
  
 <span data-ttu-id="4d985-126">가장 적합한 구현을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-126">You can choose which implementation is best for you.</span></span>  <span data-ttu-id="4d985-127">관리되는 구현은 .NET Framework를 지원하는 모든 플랫폼에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-127">The managed implementations are available on all platforms that support the .NET Framework.</span></span>  <span data-ttu-id="4d985-128">CAPI 구현은 이전 운영 체제에서 사용할 수 있으며 더 이상 개발되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-128">The CAPI implementations are available on older operating systems, and are no longer being developed.</span></span> <span data-ttu-id="4d985-129">CNG는 새로운 개발이 수행되는 최신 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-129">CNG is the very latest implementation where new development will take place.</span></span> <span data-ttu-id="4d985-130">그러나 관리되는 구현은 FIPS(Federal Information Processing Standards)에서 인증되지 않았으며 래퍼 클래스보다 느릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-130">However, the managed implementations are not certified by the Federal Information Processing Standards (FIPS), and may be slower than the wrapper classes.</span></span>  
  
## <a name="stream-design"></a><span data-ttu-id="4d985-131">스트림 디자인</span><span class="sxs-lookup"><span data-stu-id="4d985-131">Stream Design</span></span>  
 <span data-ttu-id="4d985-132">공용 언어 런타임은 대칭 알고리즘 및 해시 알고리즘을 구현하기 위한 스트림 지향 디자인을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-132">The common language runtime uses a stream-oriented design for implementing symmetric algorithms and hash algorithms.</span></span> <span data-ttu-id="4d985-133">이 디자인의 핵심은 <xref:System.Security.Cryptography.CryptoStream> 클래스로, <xref:System.IO.Stream> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-133">The core of this design is the <xref:System.Security.Cryptography.CryptoStream> class, which derives from the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="4d985-134">스트림 기반 암호화 개체는 개체의 데이터 전송 부분을 처리하는 하나의 표준 인터페이스(`CryptoStream`)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-134">Stream-based cryptographic objects support a single standard interface (`CryptoStream`) for handling the data transfer portion of the object.</span></span> <span data-ttu-id="4d985-135">모든 개체가 표준 인터페이스를 기반으로 하기 때문에 여러 개체를 함께 연결할 수 있으며(예: 해시 개체 및 암호화 개체를 순서대로 연결), 중간 저장소 없이 데이터에 대해 여러 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-135">Because all the objects are built on a standard interface, you can chain together multiple objects (such as a hash object followed by an encryption object), and you can perform multiple operations on the data without needing any intermediate storage for it.</span></span> <span data-ttu-id="4d985-136">또한 스트리밍 모델을 사용하면 더 작은 개체에서 개체를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-136">The streaming model also enables you to build objects from smaller objects.</span></span> <span data-ttu-id="4d985-137">예를 들어 스트림 개체 집합에서 이 개체를 빌드할 수도 있지만 결합된 암호화 및 해시 알고리즘을 단일 스트림 개체로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-137">For example, a combined encryption and hash algorithm can be viewed as a single stream object, although this object might be built from a set of stream objects.</span></span>  
  
## <a name="cryptographic-configuration"></a><span data-ttu-id="4d985-138">암호화 구성</span><span class="sxs-lookup"><span data-stu-id="4d985-138">Cryptographic Configuration</span></span>  
 <span data-ttu-id="4d985-139">암호화 구성을 사용하면 알고리즘의 특정 구현을 알고리즘 이름으로 확인하여 .NET Framework 암호화 클래스를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-139">Cryptographic configuration lets you resolve a specific implementation of an algorithm to an algorithm name, allowing extensibility of the .NET Framework cryptography classes.</span></span> <span data-ttu-id="4d985-140">알고리즘의 고유한 하드웨어 또는 소프트웨어 구현을 추가하고 선택한 알고리즘 이름에 해당 구현을 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-140">You can add your own hardware or software implementation of an algorithm and map the implementation to the algorithm name of your choice.</span></span> <span data-ttu-id="4d985-141">구성 파일에 알고리즘이 지정되지 않은 경우 기본 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-141">If an algorithm is not specified in the configuration file, the default settings are used.</span></span> <span data-ttu-id="4d985-142">암호화 구성에 대 한 자세한 내용은 참조 [암호화 클래스 구성](../../../docs/framework/configure-apps/configure-cryptography-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-142">For more information about cryptographic configuration, see [Configuring Cryptography Classes](../../../docs/framework/configure-apps/configure-cryptography-classes.md).</span></span>  
  
## <a name="choosing-an-algorithm"></a><span data-ttu-id="4d985-143">알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="4d985-143">Choosing an Algorithm</span></span>  
 <span data-ttu-id="4d985-144">데이터 무결성, 데이터 프라이버시 또는 키 생성과 같은 다양한 이유로 알고리즘을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-144">You can select an algorithm for different reasons: for example, for data integrity, for data privacy, or to generate a key.</span></span> <span data-ttu-id="4d985-145">대칭 및 해시 알고리즘은 무결성(변경 차단) 또는 프라이버시(보기 차단)를 위해 데이터를 보호하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-145">Symmetric and hash algorithms are intended for protecting data for either integrity reasons (protect from change) or privacy reasons (protect from viewing).</span></span> <span data-ttu-id="4d985-146">해시 알고리즘은 주로 데이터 무결성을 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-146">Hash algorithms are used primarily for data integrity.</span></span>  
  
 <span data-ttu-id="4d985-147">응용 프로그램에서 권장하는 알고리즘 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d985-147">Here is a list of recommended algorithms by application:</span></span>  
  
-   <span data-ttu-id="4d985-148">데이터 프라이버시:</span><span class="sxs-lookup"><span data-stu-id="4d985-148">Data privacy:</span></span>  
  
    -   <xref:System.Security.Cryptography.Aes>  
  
-   <span data-ttu-id="4d985-149">데이터 무결성:</span><span class="sxs-lookup"><span data-stu-id="4d985-149">Data integrity:</span></span>  
  
    -   <xref:System.Security.Cryptography.HMACSHA256>  
  
    -   <xref:System.Security.Cryptography.HMACSHA512>  
  
-   <span data-ttu-id="4d985-150">디지털 서명:</span><span class="sxs-lookup"><span data-stu-id="4d985-150">Digital signature:</span></span>  
  
    -   <xref:System.Security.Cryptography.ECDsa>  
  
    -   <xref:System.Security.Cryptography.RSA>  
  
-   <span data-ttu-id="4d985-151">키 교환:</span><span class="sxs-lookup"><span data-stu-id="4d985-151">Key exchange:</span></span>  
  
    -   <xref:System.Security.Cryptography.ECDiffieHellman>  
  
    -   <xref:System.Security.Cryptography.RSA>  
  
-   <span data-ttu-id="4d985-152">난수 생성:</span><span class="sxs-lookup"><span data-stu-id="4d985-152">Random number generation:</span></span>  
  
    -   <xref:System.Security.Cryptography.RNGCryptoServiceProvider>  
  
-   <span data-ttu-id="4d985-153">암호에서 키 생성:</span><span class="sxs-lookup"><span data-stu-id="4d985-153">Generating a key from a password:</span></span>  
  
    -   <xref:System.Security.Cryptography.Rfc2898DeriveBytes>  
  
## <a name="see-also"></a><span data-ttu-id="4d985-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d985-154">See Also</span></span>  
 [<span data-ttu-id="4d985-155">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="4d985-155">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 
