---
title: "방법: 하드웨어 암호화 장치 액세스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encryption
- key card
- cryptography
- hardware encryption
- CspParameters
ms.assetid: b0e734df-6eb4-4b16-b48c-6f0fe82d5f17
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5156316387f94d434301e2d5286bd325d7e04320
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-access-hardware-encryption-devices"></a><span data-ttu-id="bb4bc-102">방법: 하드웨어 암호화 장치 액세스</span><span class="sxs-lookup"><span data-stu-id="bb4bc-102">How to: Access Hardware Encryption Devices</span></span>
<span data-ttu-id="bb4bc-103"><xref:System.Security.Cryptography.CspParameters> 클래스를 사용하여 하드웨어 암호화 장치에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-103">You can use the <xref:System.Security.Cryptography.CspParameters> class to access hardware encryption devices.</span></span> <span data-ttu-id="bb4bc-104">예를 들어 이 클래스를 사용하여 스마트 카드, 하드웨어 난수 생성기 또는 특정 암호화 알고리즘의 하드웨어 구현과 응용 프로그램을 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-104">For example, you can use this class to integrate your application with a smart card, a hardware random number generator, or a hardware implementation of a particular cryptographic algorithm.</span></span>  
  
 <span data-ttu-id="bb4bc-105"><xref:System.Security.Cryptography.CspParameters> 클래스는 제대로 설치된 하드웨어 암호화 장치에 액세스하는 CSP(암호화 서비스 공급자)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-105">The <xref:System.Security.Cryptography.CspParameters> class creates a cryptographic service provider (CSP) that accesses a properly installed hardware encryption device.</span></span>  <span data-ttu-id="bb4bc-106">레지스트리 편집기(Regedit.exe)를 통해 다음 레지스트리 키를 검사하여 CSP의 가용성을 확인할 수 있습니다. HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-106">You can verify the availability of a CSP by inspecting the following registry key using the Registry Editor (Regedit.exe):  HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span></span>  
  
### <a name="to-sign-data-using-a-key-card"></a><span data-ttu-id="bb4bc-107">키 카드를 사용하여 데이터에 서명하려면</span><span class="sxs-lookup"><span data-stu-id="bb4bc-107">To sign data using a key card</span></span>  
  
1.  <span data-ttu-id="bb4bc-108">정수 공급자 형식과 공급자 이름을 생성자에 전달하여 <xref:System.Security.Cryptography.CspParameters> 클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-108">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2.  <span data-ttu-id="bb4bc-109">새로 만든 <xref:System.Security.Cryptography.CspParameters> 개체의 <xref:System.Security.Cryptography.CspParameters.Flags%2A> 속성에 적절한 플래그를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-109">Pass the appropriate flags to the <xref:System.Security.Cryptography.CspParameters.Flags%2A> property of the newly created <xref:System.Security.Cryptography.CspParameters> object.</span></span>  <span data-ttu-id="bb4bc-110">예를 들어 <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> 플래그를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-110">For example, pass the <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> flag.</span></span>  
  
3.  <span data-ttu-id="bb4bc-111"><xref:System.Security.Cryptography.CspParameters> 개체를 생성자에 전달하여 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 클래스(예: <xref:System.Security.Cryptography.RSACryptoServiceProvider> 클래스)의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-111">Create a new instance of an <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (for example, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class), passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
4.  <span data-ttu-id="bb4bc-112">`Sign` 메서드 중 하나를 사용하여 데이터에 서명하고 `Verify` 메서드 중 하나를 사용하여 데이터를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-112">Sign your data using one of the `Sign` methods and verify your data using one of the `Verify` methods.</span></span>  
  
### <a name="to-generate-a-random-number-using-a-hardware-random-number-generator"></a><span data-ttu-id="bb4bc-113">하드웨어 난수 생성기를 사용하여 난수를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="bb4bc-113">To generate a random number using a hardware random number generator</span></span>  
  
1.  <span data-ttu-id="bb4bc-114">정수 공급자 형식과 공급자 이름을 생성자에 전달하여 <xref:System.Security.Cryptography.CspParameters> 클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-114">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2.  <span data-ttu-id="bb4bc-115"><xref:System.Security.Cryptography.CspParameters> 개체를 생성자에 전달하여 <xref:System.Security.Cryptography.RNGCryptoServiceProvider>의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-115">Create a new instance of the <xref:System.Security.Cryptography.RNGCryptoServiceProvider>, passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
3.  <span data-ttu-id="bb4bc-116"><xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> 또는 <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> 메서드를 사용하여 난수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-116">Create a random value using the <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> or <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb4bc-117">예제</span><span class="sxs-lookup"><span data-stu-id="bb4bc-117">Example</span></span>  
 <span data-ttu-id="bb4bc-118">다음 코드 예제에서는 스마트 카드를 사용하여 데이터에 서명하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-118">The following code example demonstrates how to sign data using a smart card.</span></span>  <span data-ttu-id="bb4bc-119">코드 예제에서는 스마트 카드를 노출하는 <xref:System.Security.Cryptography.CspParameters> 개체를 만든 다음 CSP를 사용하여 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-119">The code example creates a <xref:System.Security.Cryptography.CspParameters> object that exposes a smart card, and then initializes an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object using the CSP.</span></span>  <span data-ttu-id="bb4bc-120">그런 다음 일부 데이터에 서명하고 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-120">The code example then signs and verifies some data.</span></span>  
  
 [!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
 [!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
 [!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bb4bc-121">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="bb4bc-121">Compiling the Code</span></span>  
  
-   <span data-ttu-id="bb4bc-122"><xref:System> 및 <xref:System.Security.Cryptography> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-122">Include the <xref:System> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
-   <span data-ttu-id="bb4bc-123">스마트 카드 판독기 및 드라이버가 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-123">You must have a smart card reader and drivers installed on your computer.</span></span>  
  
-   <span data-ttu-id="bb4bc-124">카드 판독기와 관련된 정보를 사용하여 <xref:System.Security.Cryptography.CspParameters> 개체를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-124">You must initialize the <xref:System.Security.Cryptography.CspParameters> object using information specific to your card reader.</span></span>  <span data-ttu-id="bb4bc-125">자세한 내용은 카드 판독기 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb4bc-125">For more information, see the documentation of your card reader.</span></span>
