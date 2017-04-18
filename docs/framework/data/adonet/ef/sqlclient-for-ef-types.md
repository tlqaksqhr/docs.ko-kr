---
title: "Entity FrameworkTypes용 SqlClient | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
caps.latest.revision: 9
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Entity FrameworkTypes용 SqlClient
\<?xml version="1.0" encoding="utf-8"?>
\<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://clixdevr3.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>.NET Framework Data Provider for SQL Server (SqlClient) 공급자 매니페스트 파일에는 공급자의 기본 형식, 개념적 모델과 저장소 모델 기본 형식 간의 승격과 변환 규칙이 개념적 모델과 저장소 모델 기본 형식 간의 매핑, 각 형식의 패싯 목록이 포함 되어 있습니다. </para> 
    <para>다음 표에서 SQL Server 2008에 대 한 형식을 설명 <token>ssVersion2005</token>, 및 <token>ssVersion2000</token> 데이터베이스 및 이러한 형식을 개념적으로 매핑하는 방법에 대 한 모델 형식입니다. 이후 버전의 SQL Server에서 도입된 몇 가지 새로운 형식은 이전 버전의 SQL Server에서는 지원되지 않습니다. 이러한 형식은 아래 표에 나와 있습니다.</para>
    \<table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
      <thead>
        <tr>
          <TD>
            <para>공급자 유형 </para> 
            <para>이름</para>
          </TD>
          <TD>
            <para>공급자 유형 </para> 
            <para>특성</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>EDMSimpleType</languageKeyword>
            </para>
            <para>이름</para>
          </TD>
          <TD>
            <para>패싯</para>
          </TD>
        </tr>
      </thead>
      <tbody>
        <tr>
          <TD>
            <para>
              <languageKeyword>비트</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm 부울</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>tinyint</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Byte</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>smallint</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Int16</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>int</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>I n t&32;</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>bigint</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Int64</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>부동 소수점</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Double</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>실제</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Double</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>10 진수</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Decimal</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>전체 자릿수</para>
                  </TD>
                  <TD>
                    <para>최소</para>
                    <para>최대</para>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>1</para>
                    <para>38</para>
                    <para>18</para>
                    <para>False</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>크기 조정</para>
                  </TD>
                  <TD>
                    <para>최소</para>
                    <para>최대</para>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>0</para>
                    <para>38</para>
                    <para>0</para>
                    <para>False</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>숫자</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Decimal</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>전체 자릿수</para>
                  </TD>
                  <TD>
                    <para>최소</para>
                    <para>최대</para>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>1</para>
                    <para>38</para>
                    <para>18</para>
                    <para>False</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>크기 조정</para>
                  </TD>
                  <TD>
                    <para>최소</para>
                    <para>최대</para>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>0</para>
                    <para>38</para>
                    <para>0</para>
                    <para>False</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>smallmoney</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Decimal</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>전체 자릿수</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>10</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>크기 조정</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>4</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>비용</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Decimal</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>전체 자릿수</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>19</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>크기 조정</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>4</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>이진 파일</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Binary</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>최소</para>
                    <para>최대</para>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>1</para>
                    <para>8000</para>
                    <para>8000</para>
                    <para>False</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>True 이면</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>varbinary</languageKeyword>
            </para>
            <para />
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Binary</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>최소</para>
                    <para>최대</para>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>1</para>
                    <para>8000</para>
                    <para>8000</para>
                    <para>False</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>varbinary (max)</languageKeyword>
            </para>
            <alert class="note">
              <para>이 유형이 지원 되지 않습니다</para>
              <para>에서 <token>ssVersion2000</token>합니다.</para>
              <para />
            </alert>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Binary</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>214748364780</para>
                    <para>true</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>이미지</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Binary</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>2147483647</para>
                    <para>true</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>타임 스탬프</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Binary</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>8</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>True 이면</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>rowversion</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Binary</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>8</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>True 이면</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>smalldatetime</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.DateTime</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>전체 자릿수</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>0</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>날짜/시간</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.DateTime</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>전체 자릿수</para>
                    <para />
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>3</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>날짜</languageKeyword>
            </para>
            <alert class="note">
              <para>이 유형이 지원 되지 않습니다</para>
              <para>SQL Server 2005 및 SQL Server 2000에 있습니다.</para>
            </alert>
            <para />
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.DateTime</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>전체 자릿수</para>
                    <para />
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>0</para>
                    <para>Flase</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>시간</languageKeyword>
            </para>
            <alert class="note">
              <para>이 유형이 지원 되지 않습니다</para>
              <para>SQL Server 2005 및 SQL Server 2000에 있습니다.</para>
              <para />
            </alert>
            <para />
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Time</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>전체 자릿수</para>
                    <para />
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>7</para>
                    <para>Flalse</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>datetime2</languageKeyword>
            </para>
            <alert class="note">
              <para>이 유형이 지원 되지 않습니다</para>
              <para>SQL Server 2005 및 SQL Server 2000에 있습니다.</para>
              <para />
            </alert>
            <para />
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.DateTime</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>전체 자릿수</para>
                    <para />
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>7</para>
                    <para>Flalse</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>datetimeoffset</languageKeyword>
            </para>
            <alert class="note">
              <para>이 유형이 지원 되지 않습니다</para>
              <para>SQL Server 2005 및 SQL Server 2000에 있습니다.</para>
            </alert>
            <para />
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.DateTimeOffset</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>전체 자릿수</para>
                    <para />
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>7</para>
                    <para>Flalse</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>nvarchar</languageKeyword>
            </para>
            <alert class="note">
              <para>이 유형이 지원 되지 않습니다</para>
              <para>에서 <token>ssVersion2000</token>합니다.</para>
            </alert>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.String</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>최소</para>
                    <para>최대</para>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>1</para>
                    <para>4000</para>
                    <para>4000</para>
                    <para>False</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>유니코드</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>True 이면</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>varchar</languageKeyword>
            </para>
            <alert class="note">
              <para>이 유형이 지원 되지 않습니다</para>
              <para>에서 <token>ssVersion2000</token>합니다.</para>
            </alert>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.String</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성</para>
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>최소</para>
                    <para>최대</para>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>1</para>
                    <para>8000</para>
                    <para>8000</para>
                    <para>False</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>유니코드</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>char</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.String</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>최소</para>
                    <para>최대</para>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>1</para>
                    <para>8000</para>
                    <para>8000</para>
                    <para>False</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>유니코드</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>True 이면</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>nchar</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.String</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>최소</para>
                    <para>최대</para>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>1</para>
                    <para>4000</para>
                    <para>4000</para>
                    <para>False</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>유니코드</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>True 이면</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>True 이면</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>varchar</languageKeyword>(<parameterReference>max</parameterReference>)</para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.String</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>2147483647</para>
                    <para>true</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>유니코드</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>nvarchar</languageKeyword>(<parameterReference>max</parameterReference>)</para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.String</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>1073741823</para>
                    <para>true</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>유니코드</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>True 이면</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>ntext</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>특성</para>
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>같은 </para> 
                    <para>비교할 수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>주문</para>
                    <para>비교할 수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.String</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>1073741823</para>
                    <para>true</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>유니코드</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>텍스트</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>같은 </para> 
                    <para>비교할 수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>주문 </para> 
                    <para>비교할 수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.String</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>2147483647</para>
                    <para>true</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>유니코드</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>고유</languageKeyword>
            </para>
            <para>
              <languageKeyword>식별자</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>특성</para>
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>같은</para>
                    <para>비교할 수</para>
                  </TD>
                  <TD>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>주문 </para> 
                    <para>비교할 수</para>
                  </TD>
                  <TD>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.Guid</languageKeyword>
            </para>
          </TD>
          <TD>
            <para>해당 없음</para>
          </TD>
        </tr>
        <tr>
          <TD>
            <para>
              <languageKeyword>xml</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>같은 </para> 
                    <para>비교할 수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>주문 </para> 
                    <para>비교할 수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
          <TD>
            <para>
              <languageKeyword>Edm.String</languageKeyword>
            </para>
          </TD>
          <TD>
            <table>
              <thead>
                <tr>
                  <TD>
                    <para>패싯 이름</para>
                  </TD>
                  <TD>
                    <para>특성 </para> 
                    <para>이름</para>
                  </TD>
                  <TD>
                    <para>값</para>
                  </TD>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <TD>
                    <para>최대 길이</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>1073741823</para>
                    <para>true</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>유니코드</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>True 이면</para>
                    <para>True</para>
                  </TD>
                </tr>
                <tr>
                  <TD>
                    <para>FixedLength</para>
                  </TD>
                  <TD>
                    <para>기본</para>
                    <para>상수</para>
                  </TD>
                  <TD>
                    <para>False</para>
                    <para>True</para>
                  </TD>
                </tr>
              </tbody>
            </table>
            <para />
          </TD>
        </tr>
      </tbody>
    </table>
  </introduction>
  <relatedTopics>
\<link xlink:href="bbdc9237-ff4c-4441-9565-31ebc29743e9">CSDL, SSDL 및 MSL 사양</link>
</relatedTopics>
</developerConceptualDocument>