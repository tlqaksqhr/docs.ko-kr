---
title: "형식화된 데이터 집합"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6ede928352c9e0f02f6ad4c27ce8f5347b868986
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="typed-datasets"></a>형식화된 데이터 집합
<xref:System.Data.DataSet>에서는 약한 형식의 변수를 통해 런타임에 바인딩하여 값에 액세스할 수도 있고 강력한 형식의 메타포를 통해 데이터에 액세스할 수도 있습니다. 테이블 및 열에 속하는 **DataSet** 알기 쉬운 이름을 사용 하 여 액세스할 수 있으며 강력한 형식의 변수입니다.  
  
 형식화 된 **DataSet** 에서 파생 되는 클래스는 **DataSet**합니다. 따라서 모든 메서드, 이벤트 및 속성을 상속는 **DataSet**합니다. 또한 형식화 된 **DataSet** 강력한 형식의 메서드, 이벤트 및 속성을 제공 합니다. 즉, 컬렉션 기반의 메서드 대신 이름을 사용하여 테이블과 열에 액세스할 수 있습니다. 형식화 된 코드의 가독성도 개선된 되지만 **DataSet** 에서는 VISUAL Studio 코드 편집기에 입력할 때 줄을 자동으로 완성 합니다.  
  
 또한 강력한 형식의 **DataSet** 컴파일 타임에 올바른 형식으로 값에 대 한 액세스를 제공 합니다. 강력한 형식의 **DataSet**, 코드 실행 시간 보다는 컴파일된은 때 형식 불일치 오류가 발생 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [강력한 형식의 데이터 집합 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 만들고 강력한 형식의 사용 하는 방법에 설명 **DataSet**합니다.  
  
 [형식화된 데이터 집합에 주석 지정](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 강력한 형식의 생성 하는 데 XML 스키마 정의 언어 (XSD) 스키마에 주석을 추가 하는 방법을 설명 **데이터 집합**, 부여할 **데이터 집합** 기본 스키마를 변경 하지 않고 요소 이름입니다.  
  
## <a name="see-also"></a>참고 항목  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
