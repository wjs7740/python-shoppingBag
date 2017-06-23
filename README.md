# Author:Jason.wang

goods = [[1,'iphone7',6000],[2,'sony',2000],[3,'imac',10000],[4,'canon',15000]]

money_total = int(input("账户余额"))
goods_buy = []
money_left = int(money_total)
while 1:
    for good in goods:
        print(good[0],'. ',good[1],' ',good[2])
    req = input("请输入购买产品的编号,结束请按q")
    if req=='q':
        break
    elif int(req) not in (1,2,3,4):
        print("输入指令有误，请重新输入")
    else:
        for good in goods:
            if req == str(good[0]):
                money_left -= int(good[2])
                if money_left<0:
                    print("余额不足")
                    money_left += int(good[2])
                else:
                    print("Add %s in your shopping bag,your current balance is \033[31;1m%s\033[0m" %(good[1],money_left))
                    goods_buy.append(good)

print("you have buy below:")
print(goods_buy)
print("your balance: ",money_left)
