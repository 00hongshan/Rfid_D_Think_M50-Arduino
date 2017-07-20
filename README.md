# D-Think_M50 Rfid ģ�� Arduino ������




# ����

![image](https://github.com/WangXuan95/Rfid_D_Think_M50-Arduino/blob/master/RFID_UNO_Connection.jpg)

ʹ�ø����ͺ� Arduino �ϵ�Ӳ�����ڻ����������D-Think_M50�����շ����ݣ����ISO15693��׼�ĵ��ӱ�ǩ��ȡ.

D-Think_M50 ģ���ڴ���Э�����ְ���������֡��װЭ�飨��datasheet��������������鷳����˷�װһ���⹩���á�

ģ�鹺��https://item.taobao.com/item.htm?id=36783593025


# ʹ��

1. ��¡�ô���⣬�����ز���ѹ.

2. �ƶ�����Ŀ¼����������README.md�ļ���Ŀ¼���� [���Arduino IDE��װĿ¼]/libraries

3. ��Arduino IDE, ��� file->examples->Rfid_D_Think_M50��������һ��ʾ���������Arduinoֻ��һ��Ӳ�����ڣ�����Arduino UNO������ѡ��readBlock_SoftSerial��������ѡ��readBlock_HardSerial.

4. ����ע�͵�ָʾ���в���.




# Rfid_D_Think_M50 ��� API ����

���з�������ģ��datasheet��д

## ���췽��

### ʹ��Ӳ�����ڣ���֪��ģ��ID��ʹ�ù㲥ID

Rfid_D_Think_M50(HardwareSerial &ser_in);

### ʹ��Ӳ�����ڣ���������֪��ģ���ַ

Rfid_D_Think_M50(HardwareSerial &ser_in, uint16_t id);

ע��ͨ������һ�������Ϲ��ض����ͬID��ģ�飬��ʡ��������

### ʹ��������ڣ���֪��ģ��ID��ʹ�ù㲥ID

Rfid_D_Think_M50(SoftwareSerial &ser_in);

### ʹ��������ڣ���������֪��ģ���ַ

Rfid_D_Think_M50(SoftwareSerial &ser_in, uint16_t id);

ע��ͨ������һ�������Ϲ��ض����ͬID��ģ�飬��ʡ��������



## ϵͳ����

���²�������ֵ��Ϊ bool��true����ɹ���false����ʧ��

### ʹ�����߲�������Ƶģʽ

bool enableAntenna(uint8_t rfidMode);

### ʹ������

bool enableAntenna();

### �ر����ߣ���СоƬ����

bool disableAntenna();

### ��ȡģ����Ϣ�ַ���

bool getModelInfo(char *infoBuffer);

### ����ģ��ID

bool setId(uint16_t id);

ע������IDΪ0x1112�����ö����ͬ��ID���Ϳ���ʵ��һ�������Ϲ��ض��ģ�飬��ʡ��������

##  ISO_15693 ����

### ��ȡ��ǩUID

bool singleInventory(uint8_t &dsfid, uint8_t uid[]);

ע�������ֱ�ǩ��Ѷ�����dsfid��8�ֽ�uid���������������true����δ���ֱ�ǩ�򷵻�false��

### ��֪��ǩUID����ȡ�����

bool read(uint8_t model, uint8_t uid[], uint8_t blockNo, uint8_t blockCnt, uint8_t data[]);

ע��model ���岻������0���ɣ�uid��Ҫ���Ŀ���uid��blockNo����Ҫ������ʼ���(ÿ��4�ֽ�)��blockCnt��Ҫ���Ŀ�����data�Ƕ��������ݵĴ���׵�ַ

### ��֪��ǩUID����ȡһ����

bool read(uint8_t model, uint8_t uid[], uint8_t blockNo, uint8_t data[]);

### �Զ����ֱ�ǩ����ȡ�����

bool read(uint8_t blockNo, uint8_t blockCnt, uint8_t data[]);

### �Զ����ֱ�ǩ����ȡһ����

bool read(uint8_t blockNo, uint8_t data[]);

### ����д�顢���顢��ȡ��״̬�ȸ���API�����Ķ� Rfid_D_Think_M50.h
