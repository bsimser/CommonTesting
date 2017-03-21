---
title: "SUM (Azure Stream Analytics)"
ms.custom: na
ms.date: "2016-04-22"
ms.prod: "azure"
ms.reviewer: na
ms.service: "stream-analytics"
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: 74d404e3-4a67-4303-b95e-d7063af3c513
caps.latest.revision: 5
ms.author: "jeffstok"
manager: "jhubbard"
translation.priority.mt: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pt-br"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
---
# SUM (Azure Stream Analytics)
  Returns the sum of all the values in the expression. SUM can be used with numeric columns only. Null values are ignored.  
  
 **Syntax**  
  
```  
SUM ( expression )  
```  
  
## Arguments  
 **expression**  
  
 Is a constant, column, or function, and any combination of arithmetic operators. SUM can be used with bigint and float columns.  
  
## Return Types  
 Returns the summation of all expression values in the most precise expression data type.  
  
## Example  
  
```  
SELECT System.TimeStamp AS OutTime, TollId, SUM (Toll)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  