---
title: "Web Services IXmlSerializable 기술 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
caps.latest.revision: 6
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: d59b8a1be0de5c2725fbb9c3421936ece4be8065
ms.contentlocale: ko-kr
ms.lasthandoff: 08/21/2017

---
# <a name="web-services-ixmlserializable-technology-sample"></a>Web Services IXmlSerializable 기술 샘플
[샘플 다운로드](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 이 샘플에서는 <xref:System.Xml.Serialization.IXmlSerializable>을 사용하여 ASP.NET 웹 서비스에서 사용자 지정 형식의 serialization을 제어하는 방법을 보여 줍니다.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Visual Studio를 사용하여 샘플을 빌드하려면  
  
1.  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]를 열고 **파일** 메뉴에서 **새 웹 사이트**를 선택합니다.  
  
2.  **새 웹 사이트** 대화 상자의 왼쪽 창에서 원하는 프로그래밍 언어를 선택한 다음 오른쪽 창에서 **ASP.NET 웹 서비스**를 선택합니다.  
  
3.  새 웹 서비스의 이름으로 **IXmlSerializable**을 입력합니다.  
  
4.  솔루션 탐색기 창에서 Service.asmx의 아이콘을 마우스 오른쪽 단추로 클릭하고 **삭제**를 선택한 다음, Service.asmx의 코드 숨김 파일에 대해 이 단계를 반복합니다.  
  
5.  프로젝트 디렉터리를 마우스 오른쪽 단추로 클릭하고 **기존 항목 추가**를 선택합니다. 대화 상자에서 언어별 디렉터리의 Service 하위 디렉터리로 이동합니다.  
  
6.  Service.asmx를 선택한 다음 Service.asmx 코드 숨김 파일에 대해 이 단계를 반복합니다.  
  
7.  [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]를 열고 위의 3단계에서 만든 IXmlSerializable 디렉터리가 있는 디렉터리로 이동합니다.  
  
8.  IXmlSerializable 디렉터리의 아이콘을 마우스 오른쪽 단추로 클릭하고 **공유 및 보안**을 선택합니다.  
  
9. 웹 공유 탭에서 **이 폴더를 공유함**을 선택하고 IXmlSerializable이라는 이름을 비롯한 기본 설정을 적용합니다.  
  
10. **확인**을 클릭합니다.  
  
### <a name="to-run-the-sample"></a>이 샘플을 실행하려면  
  
1.  브라우저 창을 열고 주소 표시줄을 선택합니다.  
  
2.  **http://localhost/IXmlSerializable/Service.asmx**를 입력합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Serialization.IXmlSerializable>   
 <xref:System.Xml.Serialization>   
 <xref:System.Xml.XmlConvert>   
 <xref:System.Xml.XmlQualifiedName>   
 <xref:System.Xml.XmlReader>   
 <xref:System.Xml.Schema.XmlSchema>   
 <xref:System.Xml.Schema.XmlSchemaSet>   
 <xref:System.Xml.XmlUrlResolver>   
 <xref:System.Xml.XmlWriter>

