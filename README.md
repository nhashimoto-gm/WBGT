# WBGT

![image](https://github.com/nhashimoto-gm/WBGT/assets/94941257/75a1f5b0-3ef4-4bf8-9ca3-c332718f3f64)

●熱中症指数（ｗｂｇｔ）の求め方

Ｔａｂｌｅから求める方法は２種類考えられます。

１）ｔａｂｌｅをデータベースとして扱い、検索する方法

 2次元配列にして、温度、湿度を整数化（コード化）すれば・・・


２）近似式を求め、計算で求める方法

 ｅｘｃｅｌで何とか実用レベルの近似式を求めました。

 
 （多変量の測定データに対して重回帰分析）
 
 ｅｘｃｅｌのソルバーではよい結果が得られず、品質工学専門家にやってもらいました。

 
 Yi*気温+Xi*湿度+YXi*気温*湿度
 
 double wbgt =0.0;
 
 double tempi =30.5, humi = 60.0;
 
 double Yi =0.90739, Xi = 0.14775;
 
 double YXi =-0.003665, aveall = 27.77;
 
 wbgt = (temp_act- tempi)*Yi;
 
 wbgt = wbgt+(hum_act- humi)*Xi;
 
 wbgt = wbgt+ (temp_act- tempi)*(hum_act- humi)*YXi+ aveall;
