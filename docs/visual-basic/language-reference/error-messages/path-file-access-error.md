---
title: "경로 파일 액세스 오류입니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c86d46c884617be152a5954426e9ddd6ef61651
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="pathfile-access-error"></a>경로/파일 액세스 오류입니다.
파일 액세스 또는 디스크 액세스 작업 중 운영 체제의 경로 파일 이름 간의 연결을 만들지 못했습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  파일 사양의 형식이 올바로 있는지 확인 합니다. 정규화 된 (절대) 또는 상대 파일 이름에 포함할 수 경로입니다. (다른 드라이브에 경로가) 하는 경우 드라이브 이름으로 정규화 된 경로 시작 하 고 파일에 루트에서 명시적인 경로 나열 합니다. 정규화 되지 않은 모든 경로 현재 드라이브와 디렉터리에 상대적입니다.  
  
2.  기존 읽기 전용 파일을 대체 하는 파일을 저장 하려고 시도 하지 않았습니다 있는지 확인 합니다. 이 경우 대상 파일의 읽기 전용 특성을 변경 또는 다른 이름으로 파일을 저장 합니다.  
  
3.  순차적 읽기 전용 파일을 열려고 하지 확인 `Output` 또는 `Append` 모드입니다. 이 경우에서 파일을 엽니다 `Input` 모드 또는 파일의 읽기 전용 특성을 변경 합니다.  
  
4.  변경 하려고 하지 않았습니다 있는지 확인 한 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 데이터베이스 또는 문서 내에서 프로젝트.  
  
## <a name="see-also"></a>참고 항목  
 [오류 형식](../../../visual-basic/programming-guide/language-features/error-types.md)
