---
title: 상속 지원
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 3d396632902b178eee34801a9716d8aa222a08d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359564"
---
# <a name="inheritance-support"></a>상속 지원
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 지원 *단일 테이블 매핑*합니다. 즉, 완전한 상속 계층이 단일 데이터베이스 테이블에 저장되어 있습니다. 테이블에는 계층 전체에 대한 모든 가능한 데이터 열의 결합된 공용 구조체가 포함됩니다. 공용 구조체는 두 개의 테이블을 이들 원래 테이블 중 어느 하나에 있는 행을 포함하는 하나의 테이블로 결합한 결과를 말합니다. 각 행은 행에 의해 표시되는 인스턴스 형식에 적용되지 않는 null을 열에 갖고 있습니다.  
  
 단일 테이블 매핑 전략은 상속을 나타내는 가장 간단한 방법이며 여러 다른 쿼리 범주에 대한 탁월한 성능 특징을 제공합니다.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 이 매핑을 구현하려면 상속 계층의 루트 클래스에서 특성 및 특성 속성을 지정해야 합니다. 자세한 내용은 참조 [하는 방법: 상속 계층 구조 매핑](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)합니다.  
  
 Visual Studio를 사용 하는 개발자 ´ ï ´는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 상속 계층 구조를 매핑할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [배경 정보](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
