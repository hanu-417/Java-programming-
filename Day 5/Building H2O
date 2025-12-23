import java.util.concurrent.Semaphore;
import java.util.concurrent.CyclicBarrier;
class H2O {
    private Semaphore hSem;
    private Semaphore oSem;
    private CyclicBarrier barrier;
    public H2O() {
        hSem = new Semaphore(2); 
        oSem = new Semaphore(1);  
        barrier = new CyclicBarrier(3); 
    }
    public void hydrogen(Runnable releaseHydrogen) throws InterruptedException {
        hSem.acquire();
        try {
            barrier.await();  
            releaseHydrogen.run();
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            hSem.release();
        }
    }
    public void oxygen(Runnable releaseOxygen) throws InterruptedException {
        oSem.acquire();
        try {
            barrier.await();  
            releaseOxygen.run();
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            oSem.release();
        }
    }
}
