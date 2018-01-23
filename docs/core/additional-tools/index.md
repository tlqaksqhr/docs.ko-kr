---
title: ".NET Core 추가 도구"
description: ".NET Core 기능을 지원하고 확장하는 추가 도구에 대한 개요입니다."
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2018
ms.topic: article
ms.prod: .net-core
ms.custom: mvc
ms.openlocfilehash: eac67285500e62501f3bb552deaf5b07db609d4e
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2018
---
# <a name="net-core-additional-tools"></a>.NET Core 추가 도구
이 섹션에서는 [.NET Core CLI (명령줄 인터페이스)](..\tools\index.md) 도구 외에 .NET Core 기능을 지원하고 확장하는 도구 목록을 컴파일합니다.

### <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[WCF Web Service Reference Tool](wcf-web-service-reference-guide.md)
WCF Web Service Reference는 [Visual Studio 2017 버전 15.5](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#WCFTools)에서 처음 공개된 Visual Studio 연결된 서비스 공급자입니다. 이 도구는 현재 솔루션, 네트워크 위치 또는 WSDL 파일의 웹 서비스에서 메타 데이터를 검색하고, 해당 웹 서비스를 액세스하는 데 사용할 수 있는 WCF(Windows Communication Foundation) 클라이언트 프록시 코드가 포함된 .NET Core 호환 소스 파일을 생성합니다.

### <a name="xml-serializer-generatorxmlserializergenerator-instructionsmd"></a>[XML Serializer Generator](xmlserializergenerator-instructions.md)
.NET Framework용 [Xml Serializer Generator(sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md)와 마찬가지로, [Microsoft.XmlSerializer.Generator NuGet 패키지](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator)는 .NET Core 및 .NET Standard 라이브러리용 솔루션입니다. <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 해당 형식의 개체를 직렬화하거나 역직렬화할 때 XML serialization의 시작 성능을 향상시키기 위해 어셈블리에 포함된 형식의 XML serialization 어셈블리를 만듭니다.
