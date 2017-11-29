---
title: "SerializationBinder를 사용하여 serialization 및 deserialization 제어"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1c3180d62824f94e27e02c80e09fdf32252f0a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a>SerializationBinder를 사용하여 serialization 및 deserialization 제어
serialization 도중에, 포맷터는 올바른 형식 및 버전의 개체 인스턴스를 만드는 데 필요한 정보를 전송합니다. 이 정보에는 일반적으로 개체에 대한 어셈블리 이름 및 전체 형식 이름이 포함됩니다. 기본적으로 deserialization은 이 정보를 사용하여 동일한 개체의 인스턴스를 만듭니다. deserialization을 수행하는 컴퓨터에 원본 클래스가 없거나, 원본 클래스가 어셈블리 간에 이동했거나, 서버와 클라이언트에 서로 다른 버전의 클래스가 필요한 경우 일부 사용자는 serialize 및 deserialize할 클래스를 제어해야 할 수 있습니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Serialization 바인더 사용](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)합니다.  
  
> [!WARNING]
>  이 기능은 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 또는 <xref:System.Runtime.Serialization.NetDataContractSerializer>를 사용할 때만 사용할 수 있습니다.  
  
## <a name="using-serializationbinder"></a>SerializationBinder 사용  
 <xref:System.Runtime.Serialization.SerializationBinder>는 serialization 및 deserialization 중에 사용되는 실제 형식을 제어하는 데 사용되는 추상 클래스입니다. Serialization 및 deserialization 중에 사용 되는 종류를 제어 하려면에서 클래스를 파생 <xref:System.Runtime.Serialization.SerializationBinder> 재정의 <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> System.String, System.String)?qualifyHint=False & autoUpgrade = True 및 <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> System.String)? qualifyHint = False & autoUpgrade = True 메서드. <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> System.String, System.String)?qualifyHint=False & autoUpgrade = True 메서드는 한 <xref:System.Type> 어셈블리 및 형식 이름을 반환 합니다. <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> System.String)?qualifyHint=False & autoUpgrade = True 메서드는 어셈블리 및 형식 이름 및 반환 된 <xref:System.Type>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Serialization 및 Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)  
 [Serialization 바인더 사용](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)
