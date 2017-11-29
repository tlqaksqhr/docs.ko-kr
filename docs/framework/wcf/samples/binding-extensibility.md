---
title: "바인딩 확장성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cabdd583-ddf5-493e-9dba-c6c31cde8f65
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61c8ae647012c5f1fffe5cf65c63b64cde62af1b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="binding-extensibility"></a><span data-ttu-id="56ff7-102">바인딩 확장성</span><span class="sxs-lookup"><span data-stu-id="56ff7-102">Binding Extensibility</span></span>
<span data-ttu-id="56ff7-103">이 단원에는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 사용자 지정 바인딩을 보여 주는 샘플이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56ff7-103">This section contains samples that demonstrate custom binding in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56ff7-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="56ff7-104">In This Section</span></span>  
 <xref:System.ServiceModel.NetHttpBinding>  
 <span data-ttu-id="56ff7-105"><xref:System.ServiceModel.Channels.HttpTransportBindingElement>의 맨 위에 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> 또는 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>를 쌓는 바인딩을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56ff7-105">Demonstrates how to implement a binding that stacks <xref:System.ServiceModel.Channels.HttpTransportBindingElement> or the <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> on top of the <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.</span></span>  
  
 <!--zz <xref:System.ServiceModel.WSStreamedHttpBinding> --> `System.ServiceModel.WSStreamedHttpBinding` 
 <span data-ttu-id="56ff7-106">HTTP 전송을 사용하는 경우 스트리밍 시나리오를 지원하도록 디자인된 바인딩을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56ff7-106">Demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>
