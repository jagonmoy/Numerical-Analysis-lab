function runge_kutta()
    x0 = 0; h = 0.1;
    f = @(t,r) 3 * exp(-t) - 0.4 * r
    x = 0:h:2;
    y = zeros(1, length(x));
    y(1) = 5;
    ret = RungeKutta(f, x0, y, x, h)
end

function ret = RungeKutta(f, x0, y, x, h)
    for i=1:(length(x)-1)                              % calculation loop
        k1 = f(x(i),y(i));
        k2 = f(x(i)+0.5*h,y(i)+0.5*h*k1);
        k3 = f((x(i)+0.5*h),(y(i)+0.5*h*k2));
        k4 = f((x(i)+h),(y(i)+k3*h));
        y(i+1) = y(i) + (1/6)*(k1+2*k2+2*k3+k4)*h;  % main equation
    end
    ret = [x', y'];
end
