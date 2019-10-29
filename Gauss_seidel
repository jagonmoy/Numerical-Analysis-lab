function gauss_seidel()
    A = [5 -2 3 0;-3 9 1 -2;2 -1 -7 1; 4 3 -5 7]
    b = [-1 2 3 0.5]'
    [x, itr] = GaussSeidel(A, b);
    if itr > 0
        fprintf('Number of iterations: %d\n', itr);
        fprintf('Solution ');x
    else
		fprintf('Abort execution!\n');
    end
end

function [x, itr] = GaussSeidel(A, b)
    fprintf("%s  %s\n", "Iteration", "root");
    x = [0 0 0 0]';
    n = size(x,1);
    normVal = Inf;
    eps = 1e-6; itr = 0;
    while normVal > eps
        x_old = x;
        for i = 1 : n
            sigma = 0;
            for j = 1 : i - 1
                    sigma = sigma + A(i,j) * x(j);
            end
            for j = i + 1 : n
                    sigma = sigma + A(i,j) * x_old(j);
            end
            x(i) = (1 / A(i,i)) * (b(i) - sigma);
        end
        itr = itr + 1;
        fprintf("%d", itr);
        x
        fprintf("\n")
        normVal = norm(x_old - x);
    end
end
