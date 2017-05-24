---
title: "방법: 사용자 지정 정책 어설션 가져오기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1f41d787-accb-4a10-bfc6-a807671d1581
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 방법: 사용자 지정 정책 어설션 가져오기
정책 어설션은 서비스 끝점의 기능 및 요구 사항에 대해 설명합니다.  클라이언트 응용 프로그램은 서비스 메타데이터에서 정책 어설션을 사용하여 서비스 끝점에 대해 서비스 계약을 사용자 지정하거나 클라이언트 바인딩을 구성할 수 있습니다.  
  
 사용자 지정 정책 어설션을 구현 하 여 가져올는 <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=fullName> 응용 프로그램 구성 파일에 입력 하는 인터페이스와 메타 데이터 시스템 또는 구현을 등록 하 여 해당 개체를 전달 합니다.  구현에서 <xref:System.ServiceModel.Description.IPolicyImportExtension> 인터페이스에는 기본 생성자를 제공 해야 합니다.  
  
### <a name="to-import-custom-policy-assertions"></a>사용자 지정 정책 어설션을 가져오려면  
  
1.  구현 된 <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=fullName> 클래스에는 인터페이스입니다. 다음 절차를 참조하십시오.  
  
2.  다음 중 하나를 사용하여 사용자 지정 정책 가져오기를 삽입합니다.  
  
3.  구성 파일 사용 다음 절차를 참조하십시오.  
  
4.  구성 파일을 사용 하 여 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다. 다음 절차를 참조하십시오.  
  
5.  정책 가져오기를 프로그래밍 방식으로 삽입 다음 절차를 참조하십시오.  
  
### <a name="to-implement-the-systemservicemodeldescriptionipolicyimportextension-interface-on-any-class"></a>클래스에서 System.ServiceModel.Description.IPolicyImportExtension 인터페이스를 구현하려면  
  
1.  에 <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=fullName> 메서드를, 관심 있는 각 정책 주체에 대 한 정책 어설션을 찾습니다 (원하는 어설션 범위에 따라 다름) 적절 한 메서드를 호출 하 여 가져올에 <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=fullName> 메서드에 전달 된 개체입니다. 다음 코드 예제를 사용 하는 방법을 보여 줍니다는 <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=fullName> 메서드를 사용자 지정 정책 어설션을 찾고 컬렉션에서 한 번에 제거 합니다. remove 메서드를 사용하여 어설션을 찾아 제거하면 4단계를 수행할 필요가 없습니다.  
  
     [!code-csharp[CustomPolicySample#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyimporter.cs#9)]
     [!code-vb[CustomPolicySample#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyimporter.vb#9)]  
  
2.  정책 어설션을 처리합니다. 정책 시스템은 중첩된 정책 및 `wsp:optional`을 정규화하지 않습니다. 따라서 정책 가져오기 확장 구현에서 이러한 구문을 처리해야 합니다.  
  
3.  정책 어설션에 의해 지정된 기능 또는 요구 사항을 지원하는 바인딩 또는 계약에 대해 사용자 지정을 수행합니다. 일반적으로 어설션은 바인딩에 특정 구성 또는 특정 바인딩 요소가 필요함을 나타냅니다. 에 액세스 하 여 다음과 같이 수정 된 <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A?displayProperty=fullName> 속성입니다. 다른 어설션을 사용하려면 계약을 수정해야 합니다.  에 액세스 하 고 사용 하 여 계약을 수정할 수는 <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A?displayProperty=fullName> 속성입니다.  정책 가져오기는 동일한 바인딩 및 계약에 대해 여러 번 호출될 수 있지만 정책 대안을 가져오는 데 실패하면 다른 정책으로 대체됩니다. 사용자 코드는 이 동작에 대해 유연해야 합니다.  
  
4.  어설션 컬렉션에서 사용자 지정 정책 어설션을 제거합니다. 어설션을 제거하지 않으면 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 정책 가져오기에 실패한 것으로 간주하고 관련 바인딩을 가져오지 않습니다. 사용 하는 경우는 <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=fullName> 메서드를 사용자 지정 정책 어설션을 검색 하 고이 단계를 수행 해야 하는 한 번에 컬렉션에서 제거 합니다.  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-a-configuration-file"></a>구성 파일을 사용하여 사용자 지정 정책 가져오기를 메타데이터 시스템에 삽입하려면  
  
1.  가져오기 형식을 추가 `<extensions>` 요소 안에 [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) 클라이언트 구성 파일의 요소입니다.  
  
     <!-- TODO: review snippet reference [!code[CustomPolicySample#7](../../../../samples/snippets/common/VS_Snippets_CFX/custompolicysample/common/client.exe.config#7)]  -->
     <!-- TODO: review snippet reference [!code-csharp[CustomPolicySample#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.exe.config#7)]  -->
     <!-- TODO: review snippet reference [!code-vb[CustomPolicySample#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/client.exe.config#7)]  -->  
  
2.  클라이언트 응용 프로그램에서 사용 하 여는 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=fullName> 또는 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName> 를 확인 및 메타 데이터 가져오기 도구를 자동으로 호출 됩니다.  
  
     [!code-csharp[CustomPolicySample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.cs#10)]
     [!code-vb[CustomPolicySample#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/client.vb#10)]  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-svcutilexe"></a>Svcutil.exe를 사용하여 사용자 지정 정책 가져오기를 메타데이터 시스템에 삽입하려면  
  
1.  가져오기 형식을 추가 `<extensions>` 요소 안에 [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) Svcutil.exe.config 구성 파일의 요소입니다. 또한 `/svcutilConfig` 옵션을 사용하여 다른 구성 파일에서 등록된 정책 가져오기 형식을 로드하도록 Svcutil.exe를 지정할 수 있습니다.  
  
2.  사용 하 여 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 가져올 메타 데이터 및 해당 가져오기가 자동으로 호출 됩니다.  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-programmatically"></a>프로그래밍 방식으로 사용자 지정 정책 가져오기를 메타데이터 시스템에 삽입하려면  
  
1.  가져오기를 추가 <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A?displayProperty=fullName> 속성 (예를 사용 하는 경우는 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName>) 메타 데이터를 가져오기 전에 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=fullName>   
 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName>   
 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=fullName>   
 [메타 데이터 시스템 확장](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)