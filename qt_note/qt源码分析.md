*** c++ 

#define Q_OBJECT \

public: \

    QT_WARNING_PUSH \ // 保存当前编译器的警告状态
    
    Q_OBJECT_NO_OVERRIDE_WARNING \ // null
    
    static const QMetaObject staticMetaObject; \ // 保存该类元对象所有信息
    
    virtual const QMetaObject *metaObject() const; \
    
    virtual void *qt_metacast(const char *); \
    
    virtual int qt_metacall(QMetaObject::Call, int, void **); \
    
    QT_TR_FUNCTIONS \

private: \

    Q_OBJECT_NO_ATTRIBUTES_WARNING \
    
    Q_DECL_HIDDEN_STATIC_METACALL static void qt_static_metacall(QObject *, QMetaObject::Call, int, void **); \
    
    QT_WARNING_POP \ // 
    
    struct QPrivateSignal {}; \
    
    QT_ANNOTATE_CLASS(qt_qobject, "")

***

### 

1. staticMetaObject静态元对象
   
   1. 
   
   2. 存储的是类对象的每个相关信息，每个相关信息的拼和
   
   3. 

## moc

### moc是什么

* moc全称Mete-Object-Compiler 元对象编译器，再bin/moc.exe

* 作用：程序编译时调用moc对工程源码进行解析，生成类的moc_xxx.cpp文件

### moc的必要性

* moc再交给gcc进行标准编译之前，先调用moc分析C++源文件，如果发现Q_OBJECT，在源文件前加上moc_生成moc_xxx.cpp将这个新文件加入编译系统  

### moc分析源文件的依据

* 依据Q_OBJECT这个宏
