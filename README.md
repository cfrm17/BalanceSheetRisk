# Balance Sheet Risk

The balance sheet model is used to determine the risks of various assets, liabilities and balance sheet items. Primarily, the model calculates the interest rate risk profile of these instruments.

The model involves defining an underlying interest rate process, valuation models for all the instruments that depends on the interest rates, and various scenarios for the interest rates in order to compute “risk profiles”.

The instruments on the balance sheet are split into various subaccounts, and these subaccounts are mapped to accounts. It is at the subaccount level that many of the instrument characteristics are defined, including cash flows, behavioral assumptions and valuation models.

Most of the subaccounts are simple, and simply project cash flows for the instruments that are not rate dependent. Therefore, most are simple discounted cash flow models. The only subaccount that was dynamic (i.e. the cash flows depended on the interest rates) were the cashable GICs.

The cashable GIC is essentially a GIC that is redeemable, and this redemption is modeled with a rate dependent function. We define the current coupon as the coupon
that would be offered on a brand new Cashable GIC as Cc, and customer coupon of the (aged) GIC to be C. In the model, the current coupon is modelled using the 1 month
spot rate.

The current refinancing incentive is the difference between
the customer coupon and the current coupon, or

	R = Cc − C,

and the maximum refinance is

	Rmax = Cmax − C.
  
The current coupon is modelled by the 1 month spot rate. Since the cashflows depend on the interest rates (through the SMM) a Monte Carlo valuation model is used.

The cashflows for these instruments depend on whether their payment frequency and the day count convention used. Denoting the amount redeemed in a given month i by
Wi, this is simply given by

	Wi = Pi−1SMM

where Pi−1 is the principal of the previous period and the principal at the end of month
i is given by Pi = Pi−1 −Wi.

Using the same notation as before, the cashflows should be Ci = Ii + Wi for all months other than maturity. At maturity, there is a
additional interest payment on the remaining principal, as well as the principal itself:

References:

https://finpricing.com/lib/EqVariance.html

https://zenodo.org/record/6548879/files/balanceSheetModel.pdf

https://zenodo.org/record/6548879#.YpDvbagpDq4





