---
title: 디지털 서명의 암호화
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
- encryption of digital signatures [WCF]
- digital signatures [WCF], encryption
- digital signatures [WCF]
ms.assetid: 0868866d-40b4-4341-8e42-eee3b7f15b69
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa6abc39159b14eae41e43de5a8976857b1d4c13
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="encryption-of-digital-signatures"></a><span data-ttu-id="9ee18-102">디지털 서명의 암호화</span><span class="sxs-lookup"><span data-stu-id="9ee18-102">Encryption of Digital Signatures</span></span>
<span data-ttu-id="9ee18-103">기본적으로 메시지는 서명 및 암호화되며 서명은 디지털 방식으로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-103">By default, a message is signed and encrypted, and the signature is digitally encrypted.</span></span> <span data-ttu-id="9ee18-104">이 작업은 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> 또는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>의 인스턴스가 포함된 사용자 지정 바인딩을 만든 다음, 해당 클래스의 `MessageProtectionOrder` 속성을 <xref:System.ServiceModel.Security.MessageProtectionOrder> 열거형 값으로 설정하여 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-104">You can control this by creating a custom binding with an instance of the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> or the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and then setting the `MessageProtectionOrder` property of either class to a <xref:System.ServiceModel.Security.MessageProtectionOrder> enumeration value.</span></span> <span data-ttu-id="9ee18-105">기본값은 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-105">The default is <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>.</span></span> <span data-ttu-id="9ee18-106">이 프로세스는 단순한 서명 및 암호화보다 10%-40%의 시간이 더 소모됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-106">This process takes 10 to 40 percent longer than simply signing and encrypting.</span></span> <span data-ttu-id="9ee18-107">하지만 서명 암호화를 사용하지 않으면 공격자가 메시지 내용을 추측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-107">Disabling encryption of the signature, however, might allow an attacker to guess the contents of the message.</span></span> <span data-ttu-id="9ee18-108">서명 요소에는 메시지의 서명된 모든 부분에 대한 일반 텍스트의 해시 코드가 들어 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-108">This is possible because the signature element contains the hash code of the plain text of every signed part in the message.</span></span> <span data-ttu-id="9ee18-109">예를 들어 메시지 본문이 기본적으로 암호화되어 있더라도 암호화되어 있지 않은 서명에는 메시지 본문에 대한 해시 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-109">For example, although the message body is encrypted by default, the unencrypted signature contains the hash code of the message body.</span></span> <span data-ttu-id="9ee18-110">따라서 메시지가 작을 경우 공격자는 그 내용을 추론할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-110">If the message is small, an attacker might be able to deduce the contents.</span></span> <span data-ttu-id="9ee18-111">서명을 암호화하면 이러한 가능성을 줄이거나 없앨 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-111">Encrypting the signature reduces or eliminates this possibility.</span></span>  
  
 <span data-ttu-id="9ee18-112">따라서 보안에 영향을 주지 않는 큰 이진 파일을 보내는 경우와 같이, 내용 가치가 낮거나 성능이 크게 향상될 경우에만 서명 암호화를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-112">Therefore, disable encryption of the signature only when the value of the content is low, and the performance gain will be significant, for example, when sending large binary files that have no security implications.</span></span>  
  
### <a name="to-disable-digital-signing"></a><span data-ttu-id="9ee18-113">디지털 서명을 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9ee18-113">To disable digital signing</span></span>  
  
1.  <span data-ttu-id="9ee18-114"><xref:System.ServiceModel.Channels.CustomBinding>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-114">Create a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span> <span data-ttu-id="9ee18-115">자세한 내용은 참조 [하는 방법: SecurityBindingElement를 사용자 지정 바인딩을 사용 하 여 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-115">For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
2.  <span data-ttu-id="9ee18-116"><xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> 또는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>를 바인딩 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-116">Add either an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> or a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> to the binding collection.</span></span>  
  
3.  <span data-ttu-id="9ee18-117"><xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> 속성을 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>로 설정하거나 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> 속성을 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-117">Set the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> property to <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>, or set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> property to <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9ee18-118"> 사용자 지정 바인딩을 만들 참조 [Creating User-Defined 바인딩](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-118"> creating custom bindings, see [Creating User-Defined Bindings](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9ee18-119"> 특정 인증 모드용 사용자 지정 바인딩을 만들어야만 참조 [하는 방법: 지정 된 인증 모드에 대 한 SecurityBindingElement 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee18-119"> creating a custom binding for a specific authentication mode, see [How to: Create a SecurityBindingElement for a Specified Authentication Mode](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee18-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ee18-120">See Also</span></span>  
 <xref:System.ServiceModel.Security.MessageProtectionOrder>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
 [<span data-ttu-id="9ee18-121">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="9ee18-121">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="9ee18-122">사용자 정의 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="9ee18-122">Creating User-Defined Bindings</span></span>](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)  
 [<span data-ttu-id="9ee18-123">방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기</span><span class="sxs-lookup"><span data-stu-id="9ee18-123">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
