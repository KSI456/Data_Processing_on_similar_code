# Data_Processing_on_similar_code

### This md file gather experience about competition.
#Daycon subject not good at modeling but good at reducing data processing time

I join competition on Daycon to the subject that distinguish what is similar code.
similar code is that result is same but detail code is not same.

First, I explain about data. data is python files as 'py' and example training sample as 'csv'
py file have 150 in one folder all of it have same result. folder have 300
so data is 150*300 py file. and print codes in one folder I find something.

That is remark. in python, remark start with '#' or start with '"""' end with '"""', or start with "'''" end with "'''"
and in python, variable declaration rarely use some special grammer like this.
ex) text1 = """happy""", text2 = '''happy''' -> print(text1) : 'happy' , print(text2) : 'happy'
and some situations start with """ end with """ in one line.

I think similar code is select 2code in one folder so I use library 'random' and using function 'set' randomly select code 2 and delete 
duplicate codes then put pandas DataFrame. but to use set code, data must str or tuple so I make data to tuple and transforme tuple to str.
but I refer to other code, make str direct way. that is shocked. Because my first approach to pandas DataFrame as string is wrong so I think
some problem string like ',' '"',"'" must pack as list or tuple. just my first approach is wrong.

but I find some incomprehensible situation, when I deal DataFrame as for or using function 'apply' It take a few times rather than
declare DataFrame using list or dictionary. I investigate why this phenomenon occur, I find some infromation from https://purplechip.tistory.com/44
so if I want to use DataFrame effectively, data processing process must do in python, not pandas. pandas function like 'apply' offer to me 660-690 minite to
data transfomer but deal with data in python and finally put in pandas DataFrame take 8-9 minite

<pre> 
<code># This method take 660~690 minite. deal data in pandas bad selection.
def process_function(df):
    print('enter_function')
    for i in range(len(df)):
        df['code1'][i] = "".join(df['code1'][0])
        df['code2'][i] = "".join(df['code2'][0])
        # print(i, end=' ')
</code>
</pre>

