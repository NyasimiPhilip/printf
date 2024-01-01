# 0x11 - Printf

## Contributors
- [Philip Nyasimi ](https://github.com/NyasimiPhilip)
- [Wilfred Ashiagbor ](https://github.com/wonka94)


    <h1>A Formatted Output Conversion C Program</h1>
    <p>This program is a pseudo-recreation of the C standard library function, printf.</p>

    <h2>Usage 🏃</h2>
    <p>To use the <code>_printf</code> function, assuming the above dependencies have been installed, compile all <code>.c</code> files in the repository and include the header <code>main.h</code> with any main function.</p>

    <h3>Example <code>main.c</code>:</h3>
    <pre><code>#include "main.h"
        int main(void)
        {
        _printf("Hello, World!");
        return (0);
        }
        Hello, World!</code></pre>
    <h2>Description 💬</h2>
    <p>The function <code>_printf</code> writes output to standard output. The function writes under the control of a format string that specifies how subsequent arguments (accessed via the variable-length argument facilities of stdarg) are converted for output.</p>
    <h3>Prototype:</h3>
    <pre><code>int _printf(const char *format, ...);</code></pre>
    <h3>Return Value</h3>
    <p>Upon successful return, <code>_printf</code> returns the number of characters printed (excluding the terminating null byte used to end output to strings). If an output error is encountered, the function returns -1.</p>
    <h3>Format of the Argument String</h3>
    <p>The format string argument is a constant character string composed of zero or more directives: ordinary characters (not %) which are copied unchanged to the output stream; and conversion specifications, each of which results in fetching zero or more subsequent arguments. Conversion specification is introduced by the character % and ends with a conversion specifier. In between the % character and conversion specifier, there may be (in order) zero or more flags, an optional minimum field width, an optional precision, and an optional length modifier. The arguments must correspond with the conversion specifier, and are used in the order given.</p>
    <h3>Flag Characters</h3>
    <p>The character % may be followed by zero or more of the following flags:</p>
    <ul>
        <li>For o conversions, the first character of the output string is prefixed with 0 if it was not zero already.</li>
        <li>For x conversions, 0x is prepended for non-zero numbers.</li>
        <li>For X conversions, 0X is prepeneded for non-zero numbers.</li>
        </ul>
    <h3>Example <code>main.c</code>:</h3>
    <pre>
    <code>int main(void)
    {
    _printf("%#x\n", 7);
    }</code>
    </pre>
    <p>Output:</p>
    <pre><code>0x7
(space)</code></pre>
    <p>A blank is left before a positive number or empty string produced by a signed conversion.</p>
    <h3>Example <code>main.c</code>:</h3>
    <pre><code>int main(void)
{
    _printf("% d\n", 7);
}</code></pre>
    <p>Output:</p>
    <pre><code> 7</code></pre>
    <p>A sign (+ or -) is always placed before a number produced by signed conversion. Overrides a space flag.</p>
    <h3>Example <code>main.c</code>:</h3>
    <pre><code>int main(void)
{
    _printf("%+d\n", 7);
}</code></pre>
    <p>Output:</p>
    <pre><code>+7</code></pre>
    <p>For d, i, o, u, x, and X conversions, the converted value is padded on the left with zeroes rather than blanks. If the 0 flag is provided to a numeric conversion with a specified precision, it is ignored.</p>
    <h3>Example <code>main.c</code>:</h3>
    <pre><code>int main(void)
{
    _printf("%05d\n", 7);
}</code></pre>
    <p>Output:</p>
    <pre><code>00007</code></pre>
    <p>The converted value is left-justified (padded on the right with blanks instead of on the left with blanks or zeroes). Overrides a 0 flag.</p>
    <h3>Example <code>main.c</code>:</h3>
    <pre><code>int main(void)
{
    _printf("%-5d7\n", 7);
}</code></pre>
    <p>Output:</p>
    <pre><code>7    7</code></pre>
    <h3>Field Width</h3>
    <p>After flags, a minimum field width may be specified by a decimal digit string. The first digit must be non-zero. If the converted value has fewer characters than the provided width, the output is padded on the left or right with spaces (depending on whether the - flag was provided).</p>
    <h3>Example <code>main.c</code>:</h3>
    <pre><code>int main(void)
{
    _printf("%7d\n", 7);
}</code></pre>
    <p>Output:</p>
    <pre><code>      7</code></pre>
    <p>Alternatively, width may be provided as an argument using the * character. For example, in the following:</p>
    <pre><code>_printf("%*d\n", 6, 1);</code></pre>
    <p>The argument 6 is considered the width for the conversion of the decimal 1.</p>
    <h3>Precision</h3>
    <p>After any flags or provided width, a precision may be specified by a '.' followed by a decimal digit string. For d, i, o, u, x, and X conversions, the precision specifies the minimum number of digits to appear. For s and S conversions, the precision specifies the maximum characters to be printed.</p>
    <h4>Example <code>main.c</code>:</h4>
    <pre><code>int main(void)
{
    _printf("%.7d\n", 7);
}</code></pre>
    <p>Output:</p>
    <pre><code>0000007</code></pre>
    <p>Alternatively, precision may be provided as an argument using the * character after the .. For example, in the following:</p>
    <pre><code>_printf("%.*d\n", 6, 1);</code></pre>
    <p>The argument 6 is considered the precision for the conversion of the decimal 


 
