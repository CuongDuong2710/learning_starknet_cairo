
## Excersice 07

assert_not_zero(value_a); // a # 0
assert_nn(value_b); // b >= 0
assert_not_equal(value_a, value_b); // a # b
assert_le(value_a, 75); // a <= 75 ( 0 <= 75 - a < RANGE)
assert_in_range(value_a, 40, 70); // 40 <= a < 70
assert_lt(value_b, 1); // b <= 1 - 1 ( 0 <= 1 - 1 - b)

> a = 60
> b = 0
>
> transaction
> https://testnet.starkscan.co/tx/0x21004f2d00237cb24e32c8d28b6a1fddb63bb8a673b07a057c995dee8a75fb8

[Math Cairo](https://github.com/starkware-libs/cairo-lang/blob/master/src/starkware/cairo/common/math.cairo)

## Exercise 09

When array =  a,b,c,d  I guess it's means

>  (d > 0 )  and (d = c * 2) and (b = c * 2) and (a = b * 2)
>
> https://testnet.starkscan.co/tx/0x5e0a396c7a46d57b8d4e52fe1871fdc475a4438ed6e2a32ab83bc1ec2d697c#overview
>
> 80, 40, 20, 10

## Exercise 10

1. Use ex10 to get ex10b address by Hex
2. Search ex10b contract on Voyager or Starkscan by address
3. Get secret value in ex10b contract
4. Return ex10 and claim_points

> ex10 address
> https://testnet.starkscan.co/contract/0x8415762f4b0b0f44e42ac1d103ac93c3ea94450a15bb65b99bbcc816a9388#write-contract
>
> ex10b address
> https://testnet.starkscan.co/contract/0x070e27636818c69fb3e17451bd077c971524cb2a5a38e79b2d8a09034b7e1a9c#read-contract
>
> transaction
> https://testnet.starkscan.co/tx/0x1f44413bf2be2d7109e631dda728a95a6af7ed6bf175a061a06af95de64572c