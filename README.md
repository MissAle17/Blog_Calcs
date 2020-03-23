# Blog_Calcs
Calculations for risk related blogging and programming

def Binomial_Option(price, time, sigma, rate):
    u = up_move(sigma, time)
    d = down_move(u)
    p_u = up_rn_prob(rate, time, d, u)
    p_d = down_rn_prob(p_u)
    s_u = up_price(price, u)
    s_d = down_price(price, d)
    c_u = future_upcall_value(price, s_u)
    c_d = future_downcall_value(price, s_d)
    ev = ev_call(c_u,p_u,c_d,p_d)
    print("The current call value is ${}".format(round(current_rn_call_value(ev,rate, time),2)))

Binomial_Option(20,1,0.14,0.04)
The current call value is $1.76