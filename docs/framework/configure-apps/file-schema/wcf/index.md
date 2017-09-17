---
title: "WCF 구성 스키마"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
caps.latest.revision: 23
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7a651746abe22b8f5eecd571b10de07b08af26bb
ms.contentlocale: ko-kr
ms.lasthandoff: 09/05/2017

---
# <a name="wcf-configuration-schema"></a>WCF 구성 스키마
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 구성 요소를 사용하면 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스 및 클라이언트 응용 프로그램을 구성할 수 있습니다. [구성 편집기 도구(SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)를 사용하여 클라이언트 및 서비스에 대한 구성 파일을 만들고 수정할 수 있습니다. 구성 파일은 XML 형식이므로 텍스트 편집기를 사용하여 구성 파일을 수동으로 편집하려면 XML에 익숙해야 합니다. 그렇지 않으면 찾을 수 없는 XML 요소 태그나 특성과 같은 문제가 발생할 수 있습니다. XML 요소 태그 및 속성이 대소문자를 구분하기 때문입니다.  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 구성 시스템은 <xref:System.Configuration> 네임스페이스를 기반으로 합니다. 따라서 응용 프로그램 및 구성의 보안을 향상시키기 위해 구성 잠금, 암호화 및 병합과 같은 <xref:System.Configuration> 네임스페이스에서 제공하는 표준 기능을 모두 사용할 수 있습니다. 이러한 개념에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
 [구성 정보 암호화](http://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [구성 설정 잠금](http://go.microsoft.com/fwlink/?LinkId=95338)  
  
 이 섹션에서는 각 구성 항목의 가능한 모든 값 및 이 값이 다른 WCF 구성 요소와 상호 작용하는 방법에 대해 설명합니다. 다음 맵에서는 WCF 구성 스키마를 보여 줍니다.  
  
 ![WCF 구성 스키마](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")  
  
> [!CAUTION]
>  잠재적 보안 위협을 방지하려면 응용 프로그램 구성 파일(app.config)에서 적절한 ACL(Access Control 목록)을 사용하여 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 구성 섹션을 보호해야 합니다.  예를 들어, 적절한 사용자만이 응용 프로그램 바인딩의 보안 설정 또는 서비스에 대한 구성 파일의 서비스 모델 섹션에 액세스하거나 이를 수정할 수 있도록 해야 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 `ServiceModel` 요소에 대해 설명합니다.  
  
 [\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 SMSvcHost.exe 도구를 구성합니다.  
  
 [\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 <xref:System.Runtime.Serialization.DataContractSerializer>와 같은 serializer를 사용하는 경우 옵션 설정의 최상위 요소입니다.  
  
## <a name="related-sections"></a>관련 단원  
 [Windows Communication Foundation 응용 프로그램 구성](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스 및 클라이언트를 구성하는 방법에 대해 설명합니다.

