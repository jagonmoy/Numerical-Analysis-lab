function newton_raphson()
	f = @(x) x^3 - 2*x^2 - 4
	x0 = 2.5;
	approximation = 1e-6
	eps = approximation;
	fprintf('\n\n')
	[solution, no_iterations] = Newton(f, x0, eps);
	if no_iterations > 0
		fprintf('Number of funtion calls: %d\n', no_iterations);
		fprintf('A solution is: %f\n', solution);
	else
		fprintf('Abort execution!\n');
	endif
end

function [solution, no_iterations] = Newton(f, x0, eps)
	pkg load symbolic
	syms n;
	ff = f(n);
	dif = diff(ff, n);
	dfdx = function_handle(dif);
	fprintf("%s\t%s\n", "Iteration", "root");
	x = x0;
	f_value = f(x);
	iteration_counter = 0;
	while abs(f_value) > eps
		f_value = f(x);
		iteration_counter = iteration_counter + 1;
		try
			x = x - (f_value) / dfdx(x);
		catch
			fprintf('Error! - derivative zero for x = %f\n', x);
			exit(1);
		end
		fprintf("%d\t\t%f\n", iteration_counter, x);
	end
	if abs(f_value) > eps
		iteration_counter = -1;
	endif
	solution = x;
	no_iterations = iteration_counter;
end
