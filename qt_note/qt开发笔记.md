* 让自定义的控件使用qss：setAttribute(Qt::WA_StyledBackground); // 启用qss

* 在QWidget及子类中，其上的控件上绘图步骤
  
  * 子控件->installEventFilter(this);
  
  * 重写eventFilter()在其中拦截QEvent::Paint事件




