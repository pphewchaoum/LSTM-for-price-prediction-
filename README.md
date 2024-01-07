
https://medium.com/@pphewchaoum/lstm-ตัวช่วยนักเทรด-ฉบับเม่า-f7022a04f4a7

ในสถานการการลงทุนที่ไม่แน่นอนยิ่งในตลาดคริปโต นั้นขาดเดาไม่ได้ มีองค์ประกอบหลายอย่าง ที่ส่งผลกับราคาของเหรียญ เช่น การทิวิตของผู้มีอิทธิพล หรือ สงครามรัฐเซีย-ยูเครน และ factor อื่นๆอีกมากมายที่ส่งผลกระทบต่อราคา และการทำกำไรของนักลงทุน

จากข้อมูลที่หยิบยกมาข้างต้น นักลงทุนส่วนมากคงประสบพบเจอกับปัญหาคล้ายๆกันแล้วเราจะทำอย่างเราได้บ้าง? เพื่อหาทางออกหรือควรวาง strategy แบบไหนถึงสามารถกำเงินออกจากตลาด 10– 1000% ต่อปีที่สามารถชนะอัตราดอกเบี้ย และเงินเฟ้อไปได้
ชวนทำความรู้แนวคิด LSTM ( Long — Short term memory ) เป็นแนวด้าน Data science ( Deep Leaning ) ที่พยามจำและวิเคราะห์สถานการณ์ที่เกิดขึ้นใกล้ที่สุด (ลำดับ sequence) ลองไปอ่านเต็มๆ ที่ Long Short-Term Memory (LSTM) พอเป็นดังนั้นเราเลยอยากลองใช้ลำดับเหตุการณ์ของการซื้อขายในตลาดและ Data ของ ETHUSDT เพื่อpredict ราคาและกำหนด strategy ผ่านการเขียน python แล้ว run model.
ขั้นตอนแรกเราต้องเตรียมData และกำหนด interval ให้เรียนร้อยโดยเราเอาข้อมูลจาก bianance API https://www.binance.com/en/landing/data ของวันที่เราต้องการtest

2. หลักจากได้ข้อมูล เราก็ทำการเขียน python เพื่อpreprocess ข้อมูลต่างๆทำการvalidate data และแบ่งdata เอาไว้ train และ test (อย่าลืม import environment ต่างๆให้เรียบร้อย)

3.เอาข้อมูลมาทำกราฟดูtrendราคา closed price ว่าแนวโน้มเป็นอย่างไรบ้าง? เพื่อศึกษาการขึ้นลงของตลาด

4.กำหนดdata ที่ต้องการจะทำการtrain( 0.2 พอไหม ? เพราะrunนานพอสมควร) และเริ่มเทรนmodel

5. หลังจาก train ข้อมูลเรียบร้อยเราลองนำ unseen data เพื่อทำงานการtestดูผลลัพธ์

จากการทำ experiment พบว่าผลของการทำprediction มีvariance ที่ต่ำมากเมื่อเทียบกับเส้นจริง
ดังนั้น การทำ LSTM เป็นmodel เชิง sequence based ซึ่งมีความน่าสนใจมากกับการนำมา predict เพื่อหาจังหวะการเข้าซื้อหรือการทำกำไร ร่วมถึงสร้าง trade bot เพื่อช่วยนักลงทุน นอกเหนือไปจาก Deep leaning แล้วเรายังใช้ basic stat ในการforcast ได้ด้วย เช่น ARIMA for Time Series Forecasting และ ARIMA เพื่อการวิเคราะห์ ETH_Price_Prediction.
สุดท้าย การ ลงทุน มีความเสี่ยง ผู้ ลงทุน ควรศึกษาข้อมูลก่อนตัดสินใจ ลงทุน
