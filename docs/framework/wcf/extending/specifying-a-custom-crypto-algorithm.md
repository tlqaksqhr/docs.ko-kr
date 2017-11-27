---
title: "사용자 지정 암호화 알고리즘 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d662a305-8e09-451d-9a59-b0f12b012f1d
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 630457e4d1b30fe2a9439c3a41af5da92606c55a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="specifying-a-custom-crypto-algorithm"></a><span data-ttu-id="bae02-102">사용자 지정 암호화 알고리즘 지정</span><span class="sxs-lookup"><span data-stu-id="bae02-102">Specifying a Custom Crypto Algorithm</span></span>
<span data-ttu-id="bae02-103">WCF를 통해 데이터를 암호화하거나 디지털 서명을 연산화할 때 사용할 사용자 지정 암호화 알고리즘을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-103">WCF allows you to specify a custom crypto algorithm to use when encrypting data or computing digital signatures.</span></span> <span data-ttu-id="bae02-104">이렇게 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-104">This is done by the following steps:</span></span>  
  
1.  <span data-ttu-id="bae02-105"><xref:System.ServiceModel.Security.SecurityAlgorithmSuite>에서 클래스를 파생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-105">Derive a class from <xref:System.ServiceModel.Security.SecurityAlgorithmSuite></span></span>  
  
2.  <span data-ttu-id="bae02-106">알고리즘을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-106">Register the algorithm</span></span>  
  
3.  <span data-ttu-id="bae02-107"><xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 파생 클래스로 바인딩을 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="bae02-107">Configure the binding with the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-derived class.</span></span>  
  
## <a name="derive-a-class-from-securityalgorithmsuite"></a><span data-ttu-id="bae02-108">SecurityAlgorithmSuite에서 클래스를 파생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-108">Derive a class from SecurityAlgorithmSuite</span></span>  
 <span data-ttu-id="bae02-109"><xref:System.ServiceModel.Security.SecurityAlgorithmSuite>는 다양한 보안 관련 작업을 수행할 때 사용할 알고리즘을 지정할 수 있도록 하는 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-109">The <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> is an abstract base class that allows you to specify the algorithm to use when performing various security related operations.</span></span> <span data-ttu-id="bae02-110">예를 들어 디지털 서명의 해시를 계산하거나 메시지를 암호화하는 작업을 수행할 때 활용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-110">For example, computing a hash for a digital signature or encrypting a message.</span></span> <span data-ttu-id="bae02-111">다음 코드에서는 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>에서 클래스를 파생하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-111">The following code shows how to derive a class from <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>:</span></span>  
  
```csharp  
public class MyCustomAlgorithmSuite : SecurityAlgorithmSuite  
    {  
        public override string DefaultAsymmetricKeyWrapAlgorithm  
        {  
            get { return SecurityAlgorithms.RsaOaepKeyWrap; }  
        }  
  
        public override string DefaultAsymmetricSignatureAlgorithm  
        {  
            get { return SecurityAlgorithms.RsaSha1Signature; }  
        }  
  
        public override string DefaultCanonicalizationAlgorithm  
        {  
            get { return SecurityAlgorithms.ExclusiveC14n; ; }  
        }  
  
        public override string DefaultDigestAlgorithm  
        {  
            get { return SecurityAlgorithms.MyCustomHashAlgorithm; }  
        }  
  
        public override string DefaultEncryptionAlgorithm  
        {  
            get { return SecurityAlgorithms.Aes128Encryption; }  
        }  
  
        public override int DefaultEncryptionKeyDerivationLength  
        {  
            get { return 128; }  
        }  
  
        public override int DefaultSignatureKeyDerivationLength  
        {  
            get { return 128; }  
        }  
  
        public override int DefaultSymmetricKeyLength  
        {  
            get { return 128; }  
        }  
  
        public override string DefaultSymmetricKeyWrapAlgorithm  
        {  
            get { return SecurityAlgorithms.Aes128Encryption; }  
        }  
  
        public override string DefaultSymmetricSignatureAlgorithm  
        {  
            get { return SecurityAlgorithms.HmacSha1Signature; }  
        }  
  
        public override bool IsAsymmetricKeyLengthSupported(int length)  
        {  
            return length >= 1024 && length <= 4096;  
        }  
  
        public override bool IsSymmetricKeyLengthSupported(int length)  
        {  
            return length >= 128 && length <= 256;  
        }  
    }  
```  
  
## <a name="register-the-custom-algorithm"></a><span data-ttu-id="bae02-112">사용자 지정 알고리즘을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-112">Register the Custom Algorithm</span></span>  
 <span data-ttu-id="bae02-113">등록은 구성 파일이나 명령적 코드에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-113">Registration can be done in a configuration file or in imperative code.</span></span> <span data-ttu-id="bae02-114">암호화 서비스 공급자를 구현하는 클래스와 별칭 간의 매핑을 만들어 사용자 지정 알고리즘을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-114">Registering a custom algorithm is done by creating a mapping between a class that implements a crypto service provider and an alias.</span></span> <span data-ttu-id="bae02-115">그런 다음 별칭은 WCF 서비스의 바인딩에서 알고리즘을 지정할 때 사용되는 URI에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-115">The alias is then mapped to a URI which is used when specifying the algorithm in the WCF service’s binding.</span></span> <span data-ttu-id="bae02-116">다음 구성 코드 조각은 구성에서 사용자 지정 알고리즘을 등록하는 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-116">The following configuration snippet illustrates how to register a custom algorithm in config:</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
           <cryptoClasses>  
              <cryptoClass SHA256CSP="System.Security.Cryptography.SHA256CryptoServiceProvider, System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
           </cryptoClasses>  
           <nameEntry name="http://constoso.com/CustomAlgorithms/CustomHashAlgorithm"  
              class="SHA256CSP" />  
           </cryptoNameMapping>  
        </cryptographySettings>  
    </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="bae02-117">아래 섹션에서 <`cryptoClasses`> 요소에서은 SHA256CryptoServiceProvider와 별칭 "SHA256CSP" 간의 매핑을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-117">The section under the <`cryptoClasses`> element creates the mapping between the SHA256CryptoServiceProvider and the alias "SHA256CSP".</span></span> <span data-ttu-id="bae02-118"><`nameEntry`> 요소는 "SHA256CSP" 별칭과 지정된 된 URL (http://constoso.com/CustomAlgorithms/CustomHashAlgorithm) 간의 매핑을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-118">The <`nameEntry`> element creates the mapping between the "SHA256CSP" alias and the specified URL (http://constoso.com/CustomAlgorithms/CustomHashAlgorithm ).</span></span>  
  
 <span data-ttu-id="bae02-119">사용 하 여 코드에서에서 사용자 지정 알고리즘을 등록 하는 <xref:System.Security.Cryptography.CryptoConfig.AddAlgorithm%2A> System.String[])?qualifyHint=False & autoUpgrade = True 메서드.</span><span class="sxs-lookup"><span data-stu-id="bae02-119">To register the custom algorithm in code use the <xref:System.Security.Cryptography.CryptoConfig.AddAlgorithm%2A> System.String[])?qualifyHint=False&autoUpgrade=True method.</span></span> <span data-ttu-id="bae02-120">이 메서드는 두 매핑을 모두 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-120">This method creates both mappings.</span></span> <span data-ttu-id="bae02-121">다음 예제에서는 이 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-121">The following example shows how to call this method:</span></span>  
  
```  
// Register the custom URI string defined for the hashAlgorithm in MyCustomAlgorithmSuite class to create the   
// SHA256CryptoServiceProvider hash algorithm object.  
CryptoConfig.AddAlgorithm(typeof(SHA256CryptoServiceProvider), "http://constoso.com/CustomAlgorithms/CustomHashAlgorithm");  
```  
  
## <a name="configure-the-binding"></a><span data-ttu-id="bae02-122">바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="bae02-122">Configure the Binding</span></span>  
 <span data-ttu-id="bae02-123">다음 코드 조각과 같이 바인딩 설정에서 사용자 지정 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 파생 클래스를 지정하여 바인딩을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bae02-123">You configure the binding by specifying the custom <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-derived class in the binding settings as shown in the following code snippet:</span></span>  
  
```csharp  
WSHttpBinding binding = new WSHttpBinding();  
            binding.Security.Message.AlgorithmSuite = new MyCustomAlgorithmSuite();  
```  
  
 <span data-ttu-id="bae02-124">전체 코드 예제에 대 한 참조는 [WCF 보안의 암호화 유연성](../../../../docs/framework/wcf/samples/cryptographic-agility-in-wcf-security.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="bae02-124">For a complete code example, see the [Cryptographic Agility in WCF Security](../../../../docs/framework/wcf/samples/cryptographic-agility-in-wcf-security.md) sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae02-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bae02-125">See Also</span></span>  
 [<span data-ttu-id="bae02-126">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="bae02-126">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="bae02-127">서비스에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="bae02-127">Securing Services</span></span>](../../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="bae02-128">보안 개요</span><span class="sxs-lookup"><span data-stu-id="bae02-128">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="bae02-129">보안 개념</span><span class="sxs-lookup"><span data-stu-id="bae02-129">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)
