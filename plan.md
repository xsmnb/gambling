BACKEND:

  write backend database query (mariadb, php) with these values:
    nickname (string, unique),
    pass (string),
    tradeurl (url, unique),
    contact email (string email, unique),
    uid (10 digit hex format, like f2b1a39c45; unique),
    balance (usd amount, cannot be less than 0)
  write mysql function that will rise or decrease (depending on providen argument: if its negative: decreaser, if positive: increase; if 0 dont do nothing) specific amount of money of specific user amount of balance
  write backend database query (mariadb, php) with these values:
    crateName (string, unique),
    timesOpened (int, default 0),
    wastedMoney (usd amount, default 0)
    itemNameList (string list)
    itemCostList (usd amount)
    dropRateList (percent value list)
    crateCost (usd amount, auto-calculated by:
      start value = 0;
      until list 'itemList' end:
        add to value itemList[n]*dropRateList[n]
      where n is index
    )
  write mysql fuction that will resolve dropped item:
    1. roll random item from specificied in argument of fuction case;
    2. calculate temp value called "helpingValue" which is equal to: cost + (wastedMoney/2)
    3. if cost of rolled item is higher than "helpingValue", roll item that's value is lower than this item
    4. calculate temp value called "fairGambling" which is equal to: crateCost - rolledItemValue
    5. increase "wastedMoney" by "fairGambling"
    6. increase "timesOpened" by one
    7. return rolled item name 

STEAM API:

  based on one acc that will magazine all tradeable items.
  write mysql function that will give to specific user's tradeurl specific item
  write mysql function that will request to specific user's tradeurl specific item

FRONTEND:

write frontend pages (tailwind, v0, shadcn-ui, js):
  login/register (sync with database!!!!),
  payment (write simulator function: let user write, how much he wanna withdraw. after that, rise his balance in database)
  main shop (ui page with clickable cases),
  cases (will decrease mount of balance depending on cost of case, but if user don have enought balance, dont let him buy),
  settings

PAYPAL:

  MODIFY simulator function: rise user's balance ONLY AFTER PAYPAL WILL SAY THAT PAYMENT IS DONE
  payment system (paypal api, paybyskins):

PAYBYSKINS:

  write function that will request via steam api the item from user, after that, increase his balance by worth of his skin
