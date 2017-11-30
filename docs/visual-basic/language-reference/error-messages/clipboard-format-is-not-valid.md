---
title: "클립보드 형식이 잘못되었습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7adc417d962de35272319d7dc976b237c7e2b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="clipboard-format-is-not-valid"></a>클립보드 형식이 잘못되었습니다.
지정 된 클립보드 형식을 실행 중인 메서드의와 호환 되지 않습니다. 이 오류의 가능한 원인:  
  
-   클립보드의를 사용 하 여 `GetText` 또는 `SetText` 메서드 이외의 클립보드 형식으로 `vbCFText` 또는 `vbCFLink`합니다.  
  
-   클립보드의를 사용 하 여 `GetData` 또는 `SetData` 메서드 이외의 클립보드 형식으로 `vbCFBitmap`, `vbCFDIB`, 또는 `vbCFMetafile`합니다.  
  
-   사용 하는 `DataObject``GetData` 메서드 또는 `SetData` 메서드 등록 된 형식 (HC000-& HFFFF), Microsoft Windows에서 예약 범위에서 클립보드 형식으로 때 해당 클립보드 형식을 등록 되지 않은 Microsoft Windows와 함께 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   잘못 된 형식을 제거 하 고 올바른을 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클립보드: 기타 서식 추가](/cpp/mfc/clipboard-adding-other-formats)
