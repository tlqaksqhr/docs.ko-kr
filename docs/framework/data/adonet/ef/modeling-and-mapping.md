---
title: 모델링 및 매핑
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 88c8786a5e538d8441e03e46e59743e4c489b4c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762938"
---
# <a name="modeling-and-mapping"></a>모델링 및 매핑
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서는 응용 프로그램에 가장 적합한 방식으로 개념적 모델, 저장소 모델 및 두 모델 간의 매핑을 정의할 수 있습니다. Visual Studio에서 엔터티 데이터 모델 도구를 사용 하면 만들 수는 있습니다. [edmx 파일](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4) 데이터베이스 또는 그래픽 모델과 업데이트 한 다음 데이터베이스나 모델이 변경 될 때 해당 파일에서 합니다.  
  
 Entity Framework 4.1부터는 Code First 개발을 통해 모델을 프로그램 방식으로 만들 수도 있습니다. Code First 개발에는 두 가지 다른 시나리오가 있습니다. 두 경우 모두 개발자는 .NET Framewor 클래스 정의를 코딩하여 모델을 정의한 후 데이터 주석 또는 fluent API를 사용하여 추가 매핑 또는 구성을 선택적으로 지정합니다.  
  
 자세한 내용은 참조 [만들고 개념적 모델을 매핑하여](http://go.microsoft.com/fwlink/?LinkId=235016)합니다.  
  
 에 포함 되어 있는 EDM 생성기 또한 사용할 수 있습니다는 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]합니다. EdmGen.exe 생성기는 기존 데이터 소스에서 .csdl, .ssdl 및 .msl 파일을 생성합니다. 또한 모델 및 매핑 콘텐츠를 수동으로 만들 수 있습니다. 자세한 내용은 참조 [EDM 생성기 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)합니다.
