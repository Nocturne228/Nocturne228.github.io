# 课程笔记

## 算法
### 第一次作业
任务一：设计一个堆栈结构，其入栈、出栈和查找最小数操作的时间复杂度均为O(1)。

代码实现：

1. 类结构
    ```cpp title="Class.cpp" linenums="1"
        class O1Stack
    {
    private:
        stack <int> elem;
        stack <int> minn;
    public:
        void push(int newelem);
        void pop();
        int min();
    }; 
    ```
2. 函数
    ```cpp title="Function.cpp" linenums="1"
    void O1Stack::push(int newelem)
    {
        this->elem.push(newelem);
        if (this->minn.empty() || newelem <= this->minn.top())
        {
            this->minn.push(newelem);
        }
        return;
    }
    void O1Stack::pop()
    {
        if (!this->minn.empty() && this->elem.top() == this->minn.top())
        {
            this->minn.pop();
        }
        if (!this->elem.empty())
            this->elem.pop();
        return;
    }
    int O1Stack::querymin()
    {
        if(this->minn.empty())
            return -1;
        return this->minn.top();
    }
    ```