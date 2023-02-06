with open("C:\\Users\\ПК\\Documents\\raa.txt") as c:
    allowedSymbols=['0','1','2','3','4','5','6','7','8','9','A','B','C','D','E','F'] ##символы 16-ричного числа
    symbol=c.read(1) ##читаем по одному символу из файла
    Result=[]
    StrNumber=""
    while len(symbol)>0: ##пока символ не "пустой"
        length=len(StrNumber)
        if allowedSymbols.__contains__(symbol): ##если прочитанный символ - символ 16-ричного числа
            StrNumber=StrNumber+symbol
        elif length>=3 and StrNumber[-3]=='A': ##когда дошли до стороннего символа, проверяем число на соотв-е усл-ю
            Number=int(StrNumber, base=16)
            Result.append(Number) ##добавляем в список число в int
            StrNumber=""
        symbol=c.read(1) ##читаем следующий символ
        if symbol=='': ##если конец файла достигнут, делаем доп.проверку, чтобы  полностью обработать последнее число
            length=len(StrNumber)
            if length>=3 and StrNumber[-3]=='A':
                Number=int(StrNumber, base=16)
                Result.append(Number)
                StrNumber=""
        if len(Result)==32: ##ограничение на длину одного списка, т.к. чисел бесконечно много
            for i in range(0, 3, 1): ##сортировка по убыванию
                for j in range(0, 3-i, 1):
                    if Result[j]<Result[j+1]:
                        m=Result[j]
                        Result[j]=Result[j+1]
                        Result[j+1]=m
            MaxinList=str(hex(Result[0])) ##вывод максимального числа из текущей последовательности  прописью
            for k in range(len(MaxinList)):
                if k!=0 and k!=1:
                    print(MaxinList[k], end=' ')
            print('\n')
           
            Result=[] ##пустой список для следующего блока чисел (новая последовательность)
