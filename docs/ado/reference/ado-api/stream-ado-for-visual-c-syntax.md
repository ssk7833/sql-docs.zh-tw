---
title: "資料流 (如需 Visual c + + 語法的 ADO) |Microsoft 文件"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
dev_langs:
- C++
helpviewer_keywords:
- Stream collection [ADO]
ms.assetid: dddcceef-9296-4fb3-8eca-94b17d0148de
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: df4137e8ce0f7651c12584cb3c679acdb3b00d32
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="stream-ado-for-visual-c-syntax"></a>(如需 Visual c + + 語法的 ADO) 資料流
## <a name="methods"></a>方法  
  
```  
Cancel(void)  
Close(void)  
CopyTo(_ADOStream *DestStream, LONG CharNumber = -1)  
Flush(void)  
LoadFromFile(BSTR FileName)  
Open(VARIANT Source, ConnectModeEnum Mode, StreamOpenOptionsEnum Options, BSTR UserName, BSTR Password)  
Read(long NumBytes, VARIANT *pVal)  
ReadText(long NumChars, BSTR *pbstr)  
SaveToFile(BSTR FileName, SaveOptionsEnum Options = adSaveCreateNotExist)  
SetEOS(void)  
SkipLine(void)  
Write(VARIANT Buffer)  
WriteText(BSTR Data, StreamWriteEnum Options = adWriteChar)  
```  
  
## <a name="properties"></a>屬性  
  
```  
get_Charset(BSTR *pbstrCharset)  
put_Charset(BSTR Charset)  
get_EOS(VARIANT_BOOL *pEOS)  
get_LineSeparator(LineSeparatorEnum *pLS)  
put_LineSeparator(LineSeparatorEnum LineSeparator)  
get_Mode(ConnectModeEnum *pMode)  
put_Mode(ConnectModeEnum Mode)  
get_Position(LONG *pPos)  
put_Position(LONG Position)  
get_Size(LONG *pSize)  
get_State(ObjectStateEnum *pState)  
get_Type(StreamTypeEnum *pType)  
put_Type(StreamTypeEnum Type)  
```  
  
## <a name="see-also"></a>另請參閱  
 [資料流物件 (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)