class ZeroEvenOdd {
    private int n;
    private AtomicInteger count;
    
    public ZeroEvenOdd(int n) {
        this.n = n;
        this.count = new AtomicInteger(0);
    }

    public void zero(IntConsumer printNumber) throws InterruptedException {
        for (int i = 0; i < n; i++) {
            while (count.get()%2==1) {
                continue;
            }
            printNumber.accept(0);
            count.getAndIncrement();
        }
    }

    public void even(IntConsumer printNumber) throws InterruptedException {
        for (int i = 2; i <= n; i+=2) {
            while (count.get()%4!=3) {
                continue;
            }
            printNumber.accept(i);
            count.getAndIncrement();
        }
    }

    public void odd(IntConsumer printNumber) throws InterruptedException {
        for (int i = 1; i <= n; i+=2) {
            while (count.get()%4!=1) {
                continue;
            }
            printNumber.accept(i);
            count.getAndIncrement();
        }
    }
}
