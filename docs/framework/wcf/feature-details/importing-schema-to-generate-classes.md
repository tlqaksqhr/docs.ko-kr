---
title: "스키마를 가져와 클래스 생성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, 스키마 가져오기 및 내보내기"
  - "XsdDataContractImporter 클래스"
ms.assetid: b9170583-8c34-43bd-97bb-6c0c8dddeee0
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# 스키마를 가져와 클래스 생성
사용할 수 있는 스키마에서 클래스를 생성 하려면 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용 하 여는 <xref:System.Runtime.Serialization.XsdDataContractImporter> 클래스입니다. 이 항목에서는 프로세스와 변형에 대해 설명합니다.  
  
## <a name="the-import-process"></a>가져오기 프로세스  
 스키마 가져오기 프로세스를 시작 하는 <xref:System.Xml.Schema.XmlSchemaSet> 하 고 생성 된 <xref:System.CodeDom.CodeCompileUnit>합니다.  
  
 `XmlSchemaSet`은 XSD(XML 스키마 정의 언어) 스키마 문서 집합을 나타내는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SOM(스키마 개체 모델)의 일부입니다. 만들려는 `XmlSchemaSet` XSD 문서 집합에서 개체, 각 문서를 deserialize는 <xref:System.Xml.Schema.XmlSchema> 개체 (사용 하 여는 <xref:System.Xml.Serialization.XmlSerializer>) 하 고 이러한 개체를 새 추가 `XmlSchemaSet`합니다.  
  
 `CodeCompileUnit`은 추상적인 방식으로 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 코드를 나타내는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] CodeDOM(코드 문서 개체 모델)의 일부입니다. 실제 코드를 생성 하는 `CodeCompileUnit`의 서브 클래스를 사용 하 여는 <xref:System.CodeDom.Compiler.CodeDomProvider> 클래스 등의 <xref:Microsoft.CSharp.CSharpCodeProvider> 또는 <xref:Microsoft.VisualBasic.VBCodeProvider> 클래스입니다.  
  
#### <a name="to-import-a-schema"></a>스키마를 가져오려면  
  
1.  인스턴스를 만들고는 <xref:System.Runtime.Serialization.XsdDataContractImporter>합니다.  
  
2.  선택적 요소. 생성자의 `CodeCompileUnit`를 전달합니다. 스키마를 가져오는 중 생성된 형식은 빈 `CodeCompileUnit`로 시작하지 않고 이 `CodeCompileUnit` 인스턴스에 추가됩니다.  
  
3.  선택적 요소. 하나를 호출 하는 <xref:System.Runtime.Serialization.XsdDataContractImporter.CanImport%2A> 메서드. 메서드는 지정된 스키마가 올바른 데이터 계약 스키마이고 가져올 수 있는지 여부를 결정합니다. `CanImport` 메서드는 `Import`(다음 단계)와 동일한 오버로드를 갖습니다.  
  
4.  오버 로드 된 중 하나를 호출 `Import` 예를 들어 메서드는 <xref:System.Runtime.Serialization.XsdDataContractImporter.Import%28System.Xml.Schema.XmlSchemaSet%29> 메서드.  
  
     가장 간단한 오버로드는 `XmlSchemaSet`를 사용하고 익명 형식을 포함하여 해당 스키마 집합에 있는 모든 형식을 가져옵니다. 다른 오버 로드를 사용 하면 XSD 형식이 나 가져올 형식 목록을 지정할 수 (의 형태로 <xref:System.Xml.XmlQualifiedName> 또는 컬렉션을 `XmlQualifiedName` 개체). 이 경우 지정된 형식만 가져옵니다. 오버 로드는 <xref:System.Xml.Schema.XmlSchemaElement> 하는 특정 요소를 가져오는 `XmlSchemaSet`, 연결 된 형식 (익명 또는 인지 하지) 형식입니다. 이 오버로드는 이 요소에 대해 생성된 형식의 데이터 계약 이름을 나타내는 `XmlQualifiedName`을 반환합니다.  
  
     `Import` 메서드를 여러 번 호출하면 동일한 `CodeCompileUnit`에 여러 항목이 추가됩니다. 형식이 이미 있으면 `CodeCompileUnit`에 생성되지 않습니다. `Import` 개체를 여러 개 사용하는 대신 동일한 `XsdDataContractImporter`에서 `XsdDataContractImporter`를 여러 번 호출합니다. 중복 형식이 생성되지 않도록 하려면 이 방법을 사용하는 것이 좋습니다.  
  
    > [!NOTE]
    >  가져오기 중 오류가 발생하면 `CodeCompileUnit`는 예기치 않은 상태가 됩니다. 실패한 가져오기에서 생성된 `CodeCompileUnit`를 사용하면 보안상 취약해질 수 있습니다.  
  
5.  액세스는 `CodeCompileUnit` 통해는 <xref:System.Runtime.Serialization.XsdDataContractImporter.CodeCompileUnit%2A> 속성입니다.  
  
### <a name="import-options-customizing-the-generated-types"></a>가져오기 옵션: 생성된 형식 사용자 지정  
 설정할 수 있습니다는 <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> 속성은 <xref:System.Runtime.Serialization.XsdDataContractImporter> 인스턴스에 <xref:System.Runtime.Serialization.ImportOptions> 가져오기 프로세스의 다양 한 측면을 제어 하는 클래스입니다. 여러 가지 옵션은 생성되는 형식에 직접 영향을 줍니다.  
  
#### <a name="controlling-the-access-level-generateinternal-or-the-internal-switch"></a>액세스 수준 제어(GenerateInternal 또는 /internal 스위치)  
 이에 해당 하는 **/ 내부** 스위치에 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.  
  
 일반적으로 public 형식은 private 필드 및 일치하는 공용 데이터 멤버 속성을 사용하여 스키마에서 생성됩니다. 대신 내부 형식을 생성 하려면 설정의 <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> 속성을 `true`합니다.  
  
 다음 예제에서는 내부 변환 되는 스키마 클래스는 <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> 속성`true.`  
  
 [!code-csharp[c_SchemaImportExport#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#2)]
 [!code-vb[c_SchemaImportExport#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#2)]  
  
#### <a name="controlling-namespaces-namespaces-or-the-namespace-switch"></a>네임스페이스 제어(Namespaces 또는 /namespace 스위치)  
 이에 해당 하는 **/namespace** 스위치에 `Svcutil.exe` 도구입니다.  
  
 일반적으로, 스키마에서 생성 된 형식으로 생성 됩니다 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 네임 스페이스, 각 XSD 네임 스페이스에 해당 하는 특정 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 에 설명 된 매핑에 따라 [데이터 계약 스키마 참조](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)합니다. 으로이 매핑을 사용자 지정할 수는 <xref:System.Runtime.Serialization.ImportOptions.Namespaces%2A> 속성을는 <xref:System.Collections.Generic.Dictionary%602>.\</TKey, TValue> 지정된 XSD 네임스페이스가 사전에 있으면 일치하는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 네임스페이스도 사전에서 가져옵니다.  
  
 예를 들어 다음 스키마를 생각해 볼 수 있습니다.  
  
 [!code[c_SchemaImportExport#10](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#10)]  
  
 다음 예제에서는 `Namespaces` 속성을 사용하여 "http://schemas.contoso.com/carSchema" 네임스페이스를 "Contoso.Cars"에 매핑합니다.  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
#### <a name="adding-the-serializableattribute-generateserializable-or-the-serializable-switch"></a>SerializableAttribute 추가(GenerateSerializable 또는 /serializable 스위치)  
 이에 해당 하는 **/serializable** 스위치에 `Svcutil.exe` 도구입니다.  
  
 경우에 따라 사용할 수는 스키마에서 생성 된 형식에 대 한 중요 한 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 런타임 serialization 엔진 (예를 들어는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> 및 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> 클래스). 이 기능은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Remoting의 형식을 사용하는 경우 유용합니다. 이 기능을 사용 하려면 적용 해야는 <xref:System.SerializableAttribute> 일반 외에도 생성된 된 형식에 특성 <xref:System.Runtime.Serialization.DataContractAttribute> 특성입니다. `GenerateSerializable` 가져오기 옵션이 `true`로 설정되어 있으면 이 특성이 자동으로 생성됩니다.  
  
 다음 예제에서는 `Vehicle` 가져오기 옵션을 `GenerateSerializable`로 설정하여 생성된 `true` 클래스를 보여 줍니다.  
  
 [!code-csharp[c_SchemaImportExport#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#4)]
 [!code-vb[c_SchemaImportExport#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#4)]  
  
#### <a name="adding-data-binding-support-enabledatabinding-or-the-enabledatabinding-switch"></a>데이터 바인딩 지원 추가(EnableDataBinding 또는 /enableDataBinding 스위치)  
 이에 해당는 **/enableDataBinding** Svcutil.exe 도구를 켭니다.  
  
 경우에 따라 스키마에서 생성된 형식을 그래픽 사용자 인터페이스 구성 요소에 바인딩하여 이러한 형식의 인스턴스를 업데이트할 경우 자동으로 UI가 업데이트되도록 할 수도 있습니다. `XsdDataContractImporter` 구현 하는 형식을 생성할 수는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스는 속성을 변경할 경우 이벤트가 트리거되는 방식에서입니다. 이 인터페이스를 지 원하는 클라이언트 UI 프로그래밍 환경에 사용할 형식을 생성 하는 경우 (예: [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)])로 설정는 <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> 속성을 `true` 이 기능을 사용 하도록 합니다.  
  
 다음 예제와 `Vehicle` 로 생성 된 클래스는 <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> 로 설정 `true`합니다.  
  
 [!code-csharp[C_SchemaImportExport#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#5)]
 [!code-vb[C_SchemaImportExport#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#5)]  
  
### <a name="import-options-choosing-collection-types"></a>가져오기 옵션: 컬렉션 형식 선택  
 XML의 두 가지 특수 패턴은 항목 컬렉션, 즉 항목 목록 및 한 항목과 다른 항목 간의 연결을 나타냅니다. 다음은 문자열 목록의 예입니다.  
  
 [!code[C_SchemaImportExport#11](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#11)]  
  
 다음은 문자열과 정수(`city name` 및 `population`) 간의 연결 예입니다.  
  
 [!code[C_SchemaImportExport#12](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#12)]  
  
> [!NOTE]
>  모든 연결을 목록으로 간주할 수도 있습니다. 예를 들어 앞의 연결을 두 개의 필드(문자열 필드 및 정수 필드)가 있는 복잡한 `city` 개체 목록으로 간주할 수 있습니다. 두 패턴은 모두 XSD 스키마에서 하나로 표현됩니다. 목록과 연결을 구분할 수 없으므로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 관련된 특별한 주석이 스키마에 없으면 해당 패턴은 항상 목록으로 처리됩니다. 주석은 지정된 패턴이 연결을 나타냄을 가리킵니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][데이터 계약 스키마 참조](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)합니다.  
  
 일반적으로 목록은 스키마가 컬렉션의 표준 명명 패턴을 따르는지 여부에 따라 제네릭 목록에서 파생된 컬렉션 데이터 계약이나 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 배열로 가져옵니다. 이에서 더 자세하게 설명 [데이터 계약의 컬렉션 형식](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md)합니다. 연결을로 가져올 일반적으로 <xref:System.Collections.Generic.Dictionary%602> 또는 사전 개체에서 파생 되는 컬렉션 데이터 계약.\</TKey, TValue> 예를 들어 다음 스키마를 생각해 볼 수 있습니다.  
  
 [!code[c_SchemaImportExport#13](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#13)]  
  
 이 스키마는 다음과 같이 가져옵니다(읽기 쉽도록 속성 대신 필드가 표시됨).  
  
 [!code-csharp[c_SchemaImportExport#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#6)]
 [!code-vb[c_SchemaImportExport#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#6)]  
  
 이러한 스키마 패턴에 대해 생성된 컬렉션 형식을 사용자 지정할 수 있습니다. 예를 들어에서 파생 된 컬렉션을 생성 하려면 수는 <xref:System.ComponentModel.BindingList%601> 대신는 <xref:System.Collections.Generic.List%601> 컬렉션의 내용이 변경 될 때 클래스 형식을 목록 상자에 바인딩하고 하 게 하기 위해 자동으로 업데이트 합니다. 이 위해 설정는 <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> 의 속성은 <xref:System.Runtime.Serialization.ImportOptions> (이후: 부터는 참조 된 형식으로) 사용할 수 있는 컬렉션 형식의 목록에 클래스입니다. 컬렉션을 가져올 때는 이 참조된 컬렉션 형식 목록이 검색되고, 가장 일치하는 컬렉션이 있으면 해당 컬렉션이 사용됩니다. 연결은 제네릭 또는 제네릭이 아닌을 구현 하는 형식에 대해서만 일치는 <xref:System.Collections.IDictionary> 목록은 지원 되는 컬렉션 형식에 대해 일치 되지만 인터페이스입니다.  
  
 예를 들어 하는 경우는 <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> 속성이로 설정 되는 <xref:System.ComponentModel.BindingList%601>, `people` 유형 앞의 예제에서는 다음과 같이 생성 됩니다.  
  
 [!code-csharp[C_SchemaImportExport#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#7)]
 [!code-vb[C_SchemaImportExport#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#7)]  
  
 폐쇄형 제네릭이 가장 일치하는 항목으로 간주됩니다. 예를 들어 경우 형식을 `BindingList(Of Integer)` 및 <xref:System.Collections.ArrayList> 전달 되는 참조 된 형식 컬렉션에 모든 스키마에 있는 정수 목록을 가져온는 `BindingList(Of Integer)`합니다. 예를 들어 다른 모든 목록 `List(Of String)`는 `ArrayList`로 가져옵니다.  
  
 제네릭 `IDictionary` 인터페이스를 구현하는 형식이 참조된 형식 컬렉션에 추가되는 경우 형식 매개 변수를 완전히 열거나 완전히 닫아야 합니다.  
  
 복제는 허용되지 않습니다. 예를 들어 `List(Of Integer)` 및 `Collection(Of Integer)`을 모두 참조된 형식에 추가할 수는 없습니다. 이렇게 하면 스키마에 정수 목록이 있을 때 사용할 항목을 결정할 수 없습니다. 중복 문제를 노출하는 형식이 스키마에 있는 경우에만 중복이 감지됩니다. 예를 들어 가져온 스키마에 정수 목록이 없는 경우 `List(Of Integer)` 및 `Collection(Of Integer)`을 참조된 형식 컬렉션에 모두 포함할 수 있지만 둘 다 영향을 미치지 않습니다.  
  
 참조된 컬렉션 형식 메커니즘은 기본 형식의 컬렉션뿐만 아니라 다른 컬렉션의 컬렉션을 비롯한 복합 형식의 컬렉션에서도 효과적으로 작동합니다.  
  
 `ReferencedCollectionTypes` 속성에 해당 하는 **/collectionType** SvcUtil.exe 도구를 켭니다. 여러 컬렉션 형식을 참조 하려면 해당는 **/collectionType** 스위치는 여러 번 지정 해야 합니다. 형식을 MsCorLib.dll에 없으면 해당 어셈블리도 참조 해야를 사용 하는 **/reference** 전환 합니다.  
  
#### <a name="import-options-referencing-existing-types"></a>가져오기 옵션: 기존 형식 참조  
 경우에 따라 스키마의 형식은 기존 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식과 일치하며 이러한 형식은 처음부터 생성할 필요가 없습니다. 이 단원의 내용은 비컬렉션 형식에만 적용됩니다. 컬렉션 형식에 대해서는 이전 단원을 참조하세요.  
  
 예를 들어 개인을 나타낼 때 항상 사용할 회사 수준의 표준 "Person" 데이터 계약 형식이 있을 수 있습니다. 일부 서비스에서 이 형식을 사용하고 서비스 메타데이터에 해당 스키마가 나타날 때마다 각 서비스에 대해 새 형식을 생성하는 대신 이 스키마를 가져올 때 기존 `Person` 형식을 다시 사용할 수 있습니다.  
  
 이 위해 목록을 전달 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 컬렉션에 다시 사용 하려면 형식에서 <xref:System.Runtime.Serialization.ImportOptions.ReferencedTypes%2A> 속성의 반환는 <xref:System.Runtime.Serialization.ImportOptions> 클래스. 이러한 형식에 스키마 형식의 이름 및 네임스페이스와 일치하는 데이터 계약 이름 및 네임스페이스가 있으면 구조 비교가 수행됩니다. 형식에 일치하는 이름과 일치하는 구조가 모두 있는 경우 새 형식을 생성하는 대신 기존 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식이 다시 사용됩니다. 이름만 일치하고 구조가 일치하지 않으면 예외가 throw됩니다. 형식을 참조할 때(예: 새 선택적 데이터 멤버를 추가할 때) 버전 관리는 허용되지 않습니다. 구조는 정확하게 일치해야 합니다.  
  
 해당 이름과 네임스페이스를 가진 스키마 형식을 가져오지 않는 한 동일한 데이터 계약 이름과 네임스페이스를 가진 여러 형식을 참조된 형식 컬렉션에 추가할 수 있습니다. 이렇게 하면 실제로 스키마에서 발생하지 않는 형식의 중복에 대해 염려하지 않고 어셈블리의 모든 형식을 쉽게 컬렉션에 추가할 수 있습니다.  
  
 `ReferencedTypes` 속성에 해당 하는 **/reference** Svcutil.exe 도구의 작업의 특정 모드에서를 전환 합니다.  
  
> [!NOTE]
>  Svcutil.exe를 사용 하는 경우 또는 (에서 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)])는 **서비스 참조 추가** MsCorLib.dll에 있는 형식의 모든 도구를 자동으로 참조 됩니다.  
  
#### <a name="import-options-importing-non-datacontract-schema-as-ixmlserializable-types"></a>가져오기 옵션: DataContract가 아닌 스키마를 IXmlSerializable 형식으로 가져오기  
 <xref:System.Runtime.Serialization.XsdDataContractImporter> 스키마의 제한 된 하위 집합을 지원 합니다. 지원되지 않는 스키마 구문이 있으면(예: XML 특성) 예외와 함께 가져오기 시도가 실패합니다. 그러나 설정 된 <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> 속성을 `true` 지원 되는 스키마 범위가 확장 됩니다. 로 설정 하면 `true`, <xref:System.Runtime.Serialization.XsdDataContractImporter> 구현 하는 형식을 생성 된 <xref:System.Xml.Serialization.IXmlSerializable> 인터페이스입니다. 이 경우 이러한 형식의 XML 표현에 직접 액세스할 수 있습니다.  
  
##### <a name="design-considerations"></a>디자인 고려 사항  
  
-   약한 형식의 XML 표현을 직접 사용하기 어려울 수도 있습니다. 와 같은 대체 serialization 엔진을 사용 하는 것이 좋습니다는 <xref:System.Xml.Serialization.XmlSerializer>,으로 강력한 형식의에서 계약을 데이터와 호환 되지 않는 스키마와 작동 하도록 합니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][XmlSerializer 클래스를 사용 하 여](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)합니다.  
  
-   일부 스키마 구문은으로 가져올 수 없는 <xref:System.Runtime.Serialization.XsdDataContractImporter> 경우에는 <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> 속성이 `true`합니다. 를 사용해 보세요는 <xref:System.Xml.Serialization.XmlSerializer> 경우가 있습니다.  
  
-   모두 되는 정확한 스키마 구문 지원 때 <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> 는 `true` 또는 `false` 에 설명 된 [데이터 계약 스키마 참조](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)합니다.  
  
-   에 대 한 스키마 생성 <xref:System.Xml.Serialization.IXmlSerializable> 형식을 가져오고 내보낼 때 충실도 유지 하지 않습니다. 즉, 생성된 형식에서 스키마를 내보내고 클래스로 가져오면 원래 스키마가 반환되지 않습니다.  
  
 결합할 수는 <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> 옵션과 함께 <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A> 앞에서 설명한 옵션입니다. 로 생성 된 형식 <xref:System.Xml.Serialization.IXmlSerializable> 구현에서는 구조적 검사를 사용 하는 경우 건너뜁니다는 <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A> 기능입니다.  
  
 <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> 옵션에 해당 하는 **/importXmlTypes** Svcutil.exe 도구를 켭니다.  
  
##### <a name="working-with-generated-ixmlserializable-types"></a>생성된 IXmlSerializable 형식 작업  
 생성 된 `IXmlSerializable` 형식에는 "nodesField" 라는 private 필드가 포함의 배열을 반환 하는 <xref:System.Xml.XmlNode> 개체입니다. 이러한 형식의 인스턴스를 deserialize하는 경우 XML 문서 개체 모델을 사용하여 이 필드를 통해 직접 XML 데이터에 액세스할 수 있습니다. 이 형식의 인스턴스를 serialize하는 경우 이 필드를 원하는 XML 데이터로 설정하면 serialize됩니다.  
  
 이 작업은 `IXmlSerializable` 구현을 통해 수행됩니다. 생성 된 `IXmlSerializable` 형식에는 <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> 구현 호출은 <xref:System.Runtime.Serialization.XmlSerializableServices.ReadNodes%2A> 의 메서드는 <xref:System.Runtime.Serialization.XmlSerializableServices> 클래스입니다. 메서드는 통해 제공 된 XML을 변환 하는 도우미 메서드는 <xref:System.Xml.XmlReader> 배열에 <xref:System.Xml.XmlNode> 개체입니다. <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> 구현은 반대를 수행 하 고 배열을 변환 `XmlNode` 개체의 시퀀스를 <xref:System.Xml.XmlWriter> 호출 합니다. 이 위해서는 사용은 <xref:System.Runtime.Serialization.XmlSerializableServices.WriteNodes%2A> 메서드.  
  
 생성된 `IXmlSerializable` 클래스에서 스키마 내보내기 프로세스를 실행할 수 있습니다. 앞에서 설명했듯이 원래 스키마가 반환되지는 않습니다. 대신 XSD 형식의 와일드카드인 “anyType” 표준 XSD 형식을 얻게 됩니다.  
  
 적용 하 여 이렇게는 <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> 를 생성 된 특성 `IXmlSerializable` 호출 하는 클래스 및 메서드를 지정 하는 <xref:System.Runtime.Serialization.XmlSerializableServices.AddDefaultSchema%2A> "anyType" 형식을 생성 하는 메서드.  
  
> [!NOTE]
>  <xref:System.Runtime.Serialization.XmlSerializableServices> 형식이이 특정 기능을 지원 하기 위해서만 존재 합니다. 다른 용도로는 사용하지 않는 것이 좋습니다.  
  
#### <a name="import-options-advanced-options"></a>가져오기 옵션: 고급 옵션  
 다음은 고급 가져오기 옵션입니다.  
  
-   <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A> 속성입니다. 지정 된 <xref:System.CodeDom.Compiler.CodeDomProvider> 생성된 된 클래스에 대 한 코드를 생성 하는 데 있습니다. 가져오기 메커니즘 기능을 피하려고 하는 <xref:System.CodeDom.Compiler.CodeDomProvider> 지원 하지 않습니다. 예를 들어 J# 언어는 제네릭을 지원하지 않습니다. 이 속성에 J# 코드 공급자를 지정 하면 가져오기의 제네릭 형식이 생성 됩니다 <xref:System.CodeDom.CodeCompileUnit>합니다. 하는 경우는 <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A> 을 설정 하지 않으면 전체 집합이 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 기능 제한 없이 사용 됩니다.  
  
-   <xref:System.Runtime.Serialization.ImportOptions.DataContractSurrogate%2A> 속성입니다. <xref:System.Runtime.Serialization.IDataContractSurrogate> 구현을이 속성을 지정할 수 있습니다. <xref:System.Runtime.Serialization.IDataContractSurrogate> 가져오기 프로세스를 사용자 지정 합니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][데이터 계약 서로게이트가](../../../../docs/framework/wcf/extending/data-contract-surrogates.md)합니다. 기본적으로 서로게이트는 사용되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.Runtime.Serialization.XsdDataContractImporter>   
 <xref:System.Runtime.Serialization.XsdDataContractExporter>   
 <xref:System.Runtime.Serialization.ImportOptions>   
 [데이터 계약 스키마 참조](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)   
 [데이터 계약 서로게이트](../../../../docs/framework/wcf/extending/data-contract-surrogates.md)   
 [스키마 가져오기 및 내보내기](../../../../docs/framework/wcf/feature-details/schema-import-and-export.md)   
 [클래스에서 스키마 내보내기](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)   
 [데이터 계약 스키마 참조](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)