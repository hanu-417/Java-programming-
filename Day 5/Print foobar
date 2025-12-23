class FooBar {
    private int n;
    private boolean isFoo = true;

    public FooBar(int n) {
        this.n = n;
    }

    public void foo(Runnable printFoo) throws InterruptedException {
        for (int i = 0; i < n; i++) {
            while(!isFoo){Thread.sleep(0, 1);}
        	printFoo.run();
            isFoo = false;
        }
    }

    public void bar(Runnable printBar) throws InterruptedException {
        for (int i = 0; i < n; i++) {
            while(isFoo){Thread.sleep(0, 1);}
        	printBar.run();
            isFoo = true;
        }
    }
}
