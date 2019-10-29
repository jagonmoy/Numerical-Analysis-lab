function bisection_method()
    f = @(x) x^3 - 2*x^2 - 4
    a = 2
    b = 3
    approximation = 1e-6
    eps = approximation;
    fprintf('\n\n')
    [solution, no_iterations] = Bisection(f, a, b, eps);
    if no_iterations > 0
		fprintf('Number of funtion calls: %d\n', no_iterations);
		fprintf('A solution is: %f\n', solution);
    else
		fprintf('Abort execution!\n');
	end
end

function [solution, no_iterations] = Bisection(f, a, b, eps)
    fprintf("%s\t%s\t\t\t%s\t\t\t%s\n", "Iteration", "a", "b", "root");
    no_iterations = 0;
    if f(a) * f(b) >= 0
        fprintf('Single root does not exist between %f and %f.\n', a, b);
        exit(1);
    endif
    solution = a;
    while abs(b - a) >= eps
        solution = (a + b) / 2;
        no_iterations = no_iterations + 1;
        if f(solution) == 0
            break;
        elseif (f(a) * f(solution)) < 0
            b = solution;
        else
            a = solution;
        end
        fprintf("%d\t\t%f\t\t%f\t\t%f\n", no_iterations, a, b, solution);
    end
end
