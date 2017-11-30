---
title: "외부 리소스 확인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad3fa320-4b8f-4e5c-b549-01157591007a
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 824a35ee5d4ecafc45167ff3f4bc89802af4ed96
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="resolving-external-resources"></a>외부 리소스 확인
**XmlResolver** 속성은 **XmlDocument** 에서 사용 되는 **XmlDocument** 외부 문서 유형 등의 XML 데이터에 인라인으로 들어 있지 않는 리소스를 찾을 클래스 정의 (Dtd), 엔터티 및 스키마를 선택 합니다. 이러한 항목은 네트워크나 로컬 드라이브에 있을 수 있으며 URI(Uniform Resource Identifier)로 식별할 수 있습니다. 이 통해는 **XmlDocument** 를 해결 하려면 **EntityReference** 노드를 문서에 있는 외부 DTD 또는 스키마에 따라 문서의 유효성을 검사 합니다.  
  
## <a name="fully-trusted-xmldocument"></a>완전 신뢰 XmlDocument  
 **XmlResolver** 속성의 기능에 적용 된 **XmlDocument.Load** 메서드. 다음 표는 방법을 **XmlDocument.XmlResolver** 속성이 작동 하는 경우는 **XmlDocument** 개체는 완전히 신뢰할 수 있는 합니다. 다음 표는 **XmlDocument.Load** 부하에 입력이 경우 메서드는 **TextReader**, **문자열**, **스트림**, 또는  **URI**합니다. 이 테이블에 적용 되지 않습니다는 **부하** 메서드 경우는 **XmlDocument** 에서 로드 되는 **XmlReader**합니다.  
  
|XmlResolver 속성|함수|참고|  
|--------------------------|--------------|-----------|  
|속성는 **XmlResolver** 클래스 속성에 사용자가 이미 설정 되었으며 이전에 만든 것입니다.|**XmlDocument** 사용 하 여는 **XmlResolver** 는 Dtd, 엔터티 및 스키마와 같은 외부 리소스에 대 한 참조를 해결 하려면 파일 이름을 확인 하기 위해 제공 됩니다.<br /><br /> **XmlResolver** 추가 또는에서 노드를 편집 하는 경우 필요한 외부 리소스 확인 하는 경우에 사용 되는 **XmlDocument**합니다.|**XmlResolver** 에 제공 된 **XmlDocument** 은 외부 리소스를 찾아 확인 해야 할 때마다 사용 되는 해결 프로그램이 합니다.|  
|속성이로 설정 되어 **null** (**Nothing** Microsoft Visual Basic.net에서).|외부 스키마나 DTD를 찾는 등 외부 리소스가 필요한 기능은 지원되지 않습니다. 외부 엔터티는 확인되지 않으며 확인이 필요한 entity 노드의 삽입과 같은 편집 기능도 수행되지 않습니다.|**XmlDocument** 로드 파일을 익명으로 및 다른 리소스를 확인 하려고 시도 하지 않습니다.|  
|속성이 설정되지 않았지만 기본 상태를 유지하고 있습니다.|**XmlUrlResolver** NULL과 자격 증명은 될 의해 인스턴스화되어 사용 되며는 **XmlDocument** 외부 Dtd, 엔터티 및 스키마, 찾기, 파일 이름을 확인할 때 및 **null** 노드를 편집할 때는 자격 증명이 사용 됩니다.||  
  
 다음 표는 **XmlDocument.Load** 메서드 경우에 대 한 입력은 **부하** 는 **XmlReader** 및 **XmlDocument** 은 완전히 신뢰 합니다.  
  
|XmlResolver 속성|함수|참고|  
|--------------------------|--------------|-----------|  
|**XmlResolver** 사용 되는 클래스는 **XmlDocument** 는 동일한 클래스에서 사용 하 고는 **XmlReader**합니다.|**XmlDocument** 사용 하 여는 **XmlResolver** 에 할당 된는 **XmlReader**합니다.<br /><br /> **XmlDocument.Resolver** 속성 설정에 관계 없이 수 없습니다는 **XmlDocument** 신뢰 수준에 방해가 되는 **XmlResolver** 에서  **XmlReader**합니다. 설정을 재정의를 시도할 수 없습니다는 **XmlReaders**' **XmlResolver** 설정 하 여는 **XmlResolver** 의 속성은 **XmlDocument**.|**XmlReader** 수는 **XmlTextReader**, **XmlValidatingReader**, 또는 사용자가 작성 한 판독기입니다. 사용되는 판독기가 엔터티 확인을 지원하면 외부 엔터티가 확인됩니다. 전달된 판독기가 엔터티 참조를 지원하지 않으면 엔터티 참조는 확인되지 않습니다.|  
  
## <a name="semi-trusted-xmldocument"></a>일부 신뢰된 XmlDocument  
 다음 표는 방법을 **XmlDocument.XmlResolver** 개체가 일부 신뢰 된 경우 속성은 사용할 수 있습니다. 이 테이블에 적용 됩니다.는 **XmlDocument.Load** 부하에 입력이 경우 메서드는 **TextReader**, **문자열**, **스트림**, 또는  **URI**합니다. 이 테이블에 적용 되지 않습니다는 **부하** 메서드 경우는 **XmlDocument** 에서 로드 되는 **XmlReader**합니다.  
  
|XmlResolver 속성|함수|참고|  
|--------------------------|--------------|-----------|  
|일부 신뢰 된 시나리오에는 **XmlResolver** 속성을 null 이외의 값으로 설정할 수 없습니다.|**XmlUrlResolver** 와 **null** 자격 증명 인스턴스화되고에서 사용 된 **XmlDocument** 외부 Dtd, 엔터티, 찾기, 파일 이름을 확인할 때 및 스키마 및 **null** 노드를 편집할 때는 자격 증명이 사용 됩니다.|이 동작은 동작과 동일 때는 **XmlResolver** 속성이 설정 되지 않았지만 왼쪽은 기본 상태에 있습니다.<br /><br /> **XmlDocument** 모든 작업에 대해 익명 권한을 사용 합니다.|  
|속성이로 설정 되어 **null** (**Nothing** Microsoft Visual Basic.net에서).|외부 스키마나 DTD를 찾는 등 외부 리소스가 필요한 기능은 지원되지 않습니다. 외부 엔터티는 확인되지 않으며 확인이 필요한 entity 노드의 삽입과 같은 편집 기능도 수행되지 않습니다.|속성이 **null**, 동작은 동일한 인지에 관계 없이 **XmlDocument** 인지 완전히 신뢰할 수 있는 일부 신뢰 합니다.|  
|속성이 설정되지 않았지만 기본 상태를 유지하고 있습니다.|**XmlUrlResolver** 와 **null** 자격 증명 인스턴스화되고에서 사용 된 **XmlDocument** 외부 Dtd, 엔터티, 찾기, 파일 이름을 확인할 때 및 스키마 및 **null** 노드를 편집할 때는 자격 증명이 사용 됩니다.|**XmlDocument** 모든 작업에 대해 익명 권한을 사용 합니다.|  
  
 이 테이블에 적용 됩니다.는 **XmlDocument.Load** 메서드 때에 대 한 입력은 **부하** 는 **XmlReader**, 및 **XmlDocument** 은 일부 신뢰 합니다.  
  
|XmlResolver 속성|함수|참고|  
|--------------------------|--------------|-----------|  
|**XmlResolver** 사용 되는 클래스는 **XmlDocument** 에서 사용 중인 것과 동일한는 **XmlReader**합니다.|**XmlDocument** 사용 하 여는 **XmlResolver** 에 할당 된는 **XmlReader**합니다.<br /><br /> **XmlDocument.Resolver** 속성 설정에 관계 없이 수 없습니다는 **XmlDocument** 신뢰 수준에 방해가 되는 **XmlResolver** 에서  **XmlReader**합니다. 설정을 재정의를 시도할 수 없습니다는 **XmlReaders** **XmlResolver** 설정 하 여는 **XmlResolver** 의 속성은 **XmlDocument**.|**XmlReader** 수는 **XmlTextReader**유효성 검사, <xref:System.Xml.XmlReader>, 또는 사용자가 작성 한 판독기입니다. 사용되는 판독기가 엔터티 확인을 지원하면 외부 엔터티가 확인됩니다. 전달된 판독기가 엔터티 참조를 지원하지 않으면 엔터티 참조는 확인되지 않습니다.|  
  
 XmlResolver가 정확한 자격 증명을 갖도록 설정하면 외부 리소스에 액세스할 수 있습니다.  
  
> [!NOTE]
>  검색할 수 없으므로 **XmlResolver** 속성입니다. 이렇게 하면 사용자가 다시 사용 하지 않도록 하려면는 **XmlResolver** 어떤 자격 증명에 설정 되었습니다. 또한 경우는 **XmlTextReader** 또는 유효성 검사 <xref:System.Xml.XmlReader> 로드 하는 데 사용 되는 **XmlDocument** 및 **XmlDocument** 해결 프로그램이 설정 된에서 해결 프로그램 이러한 판독기에서 캐시 되지 않으므로 **XmlDocument** 후의 **부하** 이 보안 위험이 있으므로/단계입니다.  
  
 자세한 내용은 <xref:System.Xml.XmlResolver> 참조 페이지의 설명 섹션을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
