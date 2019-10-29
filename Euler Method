function euler_method()
    h = 0.1
    fprintf("f(x) = -2 * ystar(x) + cos(4 * t(x))\n");
    f = @(j, l) -2 * j + cos(4 * l);
    ret = EulersMethod(h, f)
end

function ret = EulersMethod(h, f)
    t = 0:h:1;
    ystar = zeros(size(t));
    ystar(1) = 0;
    for i=1:(length(t)-1)
        k =  f(ystar(i), t(i));
        ystar(i + 1) = ystar(i) + k * h;
    end
    ret = [t', ystar'];
end
